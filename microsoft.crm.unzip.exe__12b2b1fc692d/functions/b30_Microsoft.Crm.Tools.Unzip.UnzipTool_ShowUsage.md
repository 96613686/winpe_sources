# Microsoft.Crm.Tools.Unzip.UnzipTool::ShowUsage

- ea: `0xb30`
- end: `0xb4f`
- name: `Microsoft.Crm.Tools.Unzip.UnzipTool::ShowUsage`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2e0`

## string_xrefs

- `0xb44`: `  Try: Microsoft.Crm.Unzip.exe <zip file path> <target directory> <max allowed content file size>`

## pseudocode

```c

```

## disassembly

```asm
0xb30  ldstr    aUnzipTool// "  Unzip tool: "
0xb35  call     void [mscorlib]System.Console::WriteLine(string)
0xb3a  ldstr    asc_1790// ""
0xb3f  call     void [mscorlib]System.Console::WriteLine(string)
0xb44  ldstr    aTryMicrosoftCr// "  Try: Microsoft.Crm.Unzip.exe <zip fil"...
0xb49  call     void [mscorlib]System.Console::WriteLine(string)
0xb4e  ret
```
