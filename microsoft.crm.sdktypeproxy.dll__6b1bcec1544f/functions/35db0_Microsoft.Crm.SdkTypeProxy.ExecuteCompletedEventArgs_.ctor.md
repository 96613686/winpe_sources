# Microsoft.Crm.SdkTypeProxy.ExecuteCompletedEventArgs::.ctor

- ea: `0x35db0`
- end: `0x35dc2`
- name: `Microsoft.Crm.SdkTypeProxy.ExecuteCompletedEventArgs::.ctor`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x320`

## pseudocode

```c

```

## disassembly

```asm
0x35db0  ldarg.0
0x35db1  ldarg.2
0x35db2  ldarg.3
0x35db3  ldarg.s  4
0x35db5  call     instance void [System]System.ComponentModel.AsyncCompletedEventArgs::.ctor(class [mscorlib]System.Exception, bool, object)
0x35dba  ldarg.0
0x35dbb  ldarg.1
0x35dbc  stfld    object[] Microsoft.Crm.SdkTypeProxy.ExecuteCompletedEventArgs::results
0x35dc1  ret
```
