# Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace

- ea: `0xb10`
- end: `0xb28`
- name: `Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace`
- size: `24`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2e0`
- `0x400`
- `0x680`
- `0x6f0`
- `0xa20`

## pseudocode

```c

```

## disassembly

```asm
0xb10  ldstr    a0// "{0}:"
0xb15  ldarg.1
0xb16  box      [System]System.Diagnostics.TraceLevel
0xb1b  call     void [mscorlib]System.Console::WriteLine(string, object)
0xb20  ldarg.2
0xb21  ldarg.3
0xb22  call     void [mscorlib]System.Console::WriteLine(string, object[])
0xb27  ret
```
