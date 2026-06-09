# Microsoft.Crm.Sandbox.SandboxUtility::SandboxFilesPath

- ea: `0x2d10`
- end: `0x2d2d`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::SandboxFilesPath`
- size: `29`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2d30`
- `0x2d70`
- `0x2d90`
- `0x2db0`
- `0x2de0`

## string_xrefs

- `0x2d18`: `filesPath`

## pseudocode

```c

```

## disassembly

```asm
0x2d10  ldc.i4.s 0x1C
0x2d12  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x2d17  dup
0x2d18  ldstr    aFilespath// "filesPath"
0x2d1d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2d22  ldstr    aMicrosoftMscrm// "Microsoft\\MSCRM\\"
0x2d27  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2d2c  ret
```
