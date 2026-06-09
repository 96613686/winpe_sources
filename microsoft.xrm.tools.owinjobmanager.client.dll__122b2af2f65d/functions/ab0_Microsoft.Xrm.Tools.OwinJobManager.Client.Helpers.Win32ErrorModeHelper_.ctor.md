# Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.Win32ErrorModeHelper::.ctor

- ea: `0xab0`
- end: `0xac3`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.Win32ErrorModeHelper::.ctor`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x510`

## callees

- `0xaa0`

## pseudocode

```c

```

## disassembly

```asm
0xab0  ldarg.0
0xab1  call     instance void [mscorlib]System.Object::.ctor()
0xab6  ldarg.0
0xab7  ldc.i4.3
0xab8  call     int32 Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.Win32ErrorModeHelper::SetErrorMode(int32 mode)
0xabd  stfld    int32 Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.Win32ErrorModeHelper::oldErrorMode
0xac2  ret
```
