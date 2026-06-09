# Microsoft.Crm.SdkTypeProxy.FetchCompletedEventArgs::.ctor

- ea: `0x35e50`
- end: `0x35e62`
- name: `Microsoft.Crm.SdkTypeProxy.FetchCompletedEventArgs::.ctor`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x420`

## pseudocode

```c

```

## disassembly

```asm
0x35e50  ldarg.0
0x35e51  ldarg.2
0x35e52  ldarg.3
0x35e53  ldarg.s  4
0x35e55  call     instance void [System]System.ComponentModel.AsyncCompletedEventArgs::.ctor(class [mscorlib]System.Exception, bool, object)
0x35e5a  ldarg.0
0x35e5b  ldarg.1
0x35e5c  stfld    object[] Microsoft.Crm.SdkTypeProxy.FetchCompletedEventArgs::results
0x35e61  ret
```
