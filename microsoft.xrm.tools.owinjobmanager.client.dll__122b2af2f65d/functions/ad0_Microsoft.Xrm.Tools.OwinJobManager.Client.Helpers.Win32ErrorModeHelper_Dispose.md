# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.Win32ErrorModeHelper::Dispose

- ea: `0xad0`
- end: `0xadd`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.Win32ErrorModeHelper::Dispose`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xaa0`

## pseudocode

```c

```

## disassembly

```asm
0xad0  ldarg.0
0xad1  ldfld    int32 Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.Win32ErrorModeHelper::oldErrorMode
0xad6  call     int32 Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.Win32ErrorModeHelper::SetErrorMode(int32 mode)
0xadb  pop
0xadc  ret
```
