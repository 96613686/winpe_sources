# Microsoft.Crm.SdkTypeProxy.RetrieveMultipleCompletedEventArgs::.ctor

- ea: `0x36080`
- end: `0x36092`
- name: `Microsoft.Crm.SdkTypeProxy.RetrieveMultipleCompletedEventArgs::.ctor`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x850`

## pseudocode

```c

```

## disassembly

```asm
0x36080  ldarg.0
0x36081  ldarg.2
0x36082  ldarg.3
0x36083  ldarg.s  4
0x36085  call     instance void [System]System.ComponentModel.AsyncCompletedEventArgs::.ctor(class [mscorlib]System.Exception, bool, object)
0x3608a  ldarg.0
0x3608b  ldarg.1
0x3608c  stfld    object[] Microsoft.Crm.SdkTypeProxy.RetrieveMultipleCompletedEventArgs::results
0x36091  ret
```
