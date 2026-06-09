# Microsoft.Crm.Tools.Unzip.UnzipTool::.ctor

- ea: `0xb50`
- end: `0xbc2`
- name: `Microsoft.Crm.Tools.Unzip.UnzipTool::.ctor`
- size: `114`
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
0xb50  ldarg.0
0xb51  ldsfld   string [mscorlib]System.String::Empty
0xb56  stfld    string Microsoft.Crm.Tools.Unzip.UnzipTool::zipFilePath
0xb5b  ldarg.0
0xb5c  ldsfld   string [mscorlib]System.String::Empty
0xb61  stfld    string Microsoft.Crm.Tools.Unzip.UnzipTool::unzipFolderPath
0xb66  ldarg.0
0xb67  ldc.i4   0x2000000
0xb6c  stfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxContentFileSize
0xb71  ldarg.0
0xb72  ldc.i4.s 0x19
0xb74  stfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::cumulativeFileSizeFactor
0xb79  ldarg.0
0xb7a  ldc.i4   0x32000000
0xb7f  stfld    int32 Microsoft.Crm.Tools.Unzip.UnzipTool::maxCumulativeFileSize
0xb84  ldarg.0
0xb85  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xb8a  dup
0xb8b  ldstr    aCsv// ".csv"
0xb90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xb95  dup
0xb96  ldstr    aTxt// ".txt"
0xb9b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xba0  dup
0xba1  ldstr    aXml// ".xml"
0xba6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbab  dup
0xbac  ldstr    aXlsx// ".xlsx"
0xbb1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbb6  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.Unzip.UnzipTool::ValidFileTypes
0xbbb  ldarg.0
0xbbc  call     instance void [mscorlib]System.Object::.ctor()
0xbc1  ret
```
