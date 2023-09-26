#!/usr/bin/env zsh

if [ $# -ne 1 ]; then
  echo "Usage: $0 <template\ name>"
  exit 1
fi

name="$1"

input_file="template-text.txt"
template_dir=~/Library/Developer/Xcode/Templates/File\ Templates/MultiPlatform/Source/$name.xctemplate
demand='<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"><plist version="1.0"><dict><key>SupportsSwiftPackage</key><true/><key>Kind</key><string>Xcode.IDEFoundation.TextSubstitutionFileTemplateKind</string><key>Description</key><string>A no comment Swift file.</string><key>Summary</key><string>A no comment Swift file</string><key>SortOrder</key><string>1</string><key>Image</key><dict><key>FileTypeIcon</key><string>swift</string></dict><key>AllowedTypes</key><array><string>public.swift-source</string></array><key>Platforms</key><array/><key>DefaultCompletionName</key><string>File</string><key>MainTemplateFile</key><string>___FILEBASENAME___.swift</string></dict></plist>'

if [ ! -d "$template_dir" ]; then
  mkdir -p "$template_dir"
fi

echo $demand > "$template_dir/TemplateInfo.plist"
cat $input_file > "$template_dir/___FILEBASENAME___.swift"

echo "Done"
