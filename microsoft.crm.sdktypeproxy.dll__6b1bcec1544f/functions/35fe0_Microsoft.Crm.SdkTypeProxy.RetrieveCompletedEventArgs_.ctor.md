# Microsoft.Crm.SdkTypeProxy.RetrieveCompletedEventArgs::.ctor

- ea: `0x35fe0`
- end: `0x35ff2`
- name: `Microsoft.Crm.SdkTypeProxy.RetrieveCompletedEventArgs::.ctor`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x750`

## pseudocode

```c

```

## disassembly

```asm
0x35fe0  ldarg.0
0x35fe1  ldarg.2
0x35fe2  ldarg.3
0x35fe3  ldarg.s  4
0x35fe5  call     instance void [System]System.ComponentModel.AsyncCompletedEventArgs::.ctor(class [mscorlib]System.Exception, bool, object)
0x35fea  ldarg.0
0x35feb  ldarg.1
0x35fec  stfld    object[] Microsoft.Crm.SdkTypeProxy.RetrieveCompletedEventArgs::results
0x35ff1  ret
```
