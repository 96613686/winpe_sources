# Microsoft.Crm.Tools.Unzip.UnzipTool::ParseArguments

- ea: `0x3c0`
- end: `0x3f9`
- name: `Microsoft.Crm.Tools.Unzip.UnzipTool::ParseArguments`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2e0`

## pseudocode

```c

```

## disassembly

```asm
0x3c0  ldarg.0
0x3c1  ldarg.1
0x3c2  ldc.i4.0
0x3c3  ldelem.ref
0x3c4  stfld    string Microsoft.Crm.Tools.Unzip.UnzipTool::zipFilePath
0x3c9  ldarg.0
0x3ca  ldarg.1
0x3cb  ldc.i4.1
0x3cc  ldelem.ref
0x3cd  stfld    string Microsoft.Crm.Tools.Unzip.UnzipTool::unzipFolderPath
0x3d2  ldarg.0
0x3d3  ldarg.1
0x3d4  ldc.i4.2
0x3d5  ldelem.ref
0x3d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3db  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x3e0  stfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxContentFileSize
0x3e5  ldarg.0
0x3e6  ldarg.0
0x3e7  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxContentFileSize
0x3ec  ldarg.0
0x3ed  ldfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::cumulativeFileSizeFactor
0x3f2  mul
0x3f3  stfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxCumulativeFileSize
0x3f8  ret
```
