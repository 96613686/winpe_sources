# Microsoft.Crm.SdkTypeProxy.Metadata.ExecuteCompletedEventArgs::.ctor

- ea: `0x373d0`
- end: `0x373e2`
- name: `Microsoft.Crm.SdkTypeProxy.Metadata.ExecuteCompletedEventArgs::.ctor`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x36280`

## pseudocode

```c

```

## disassembly

```asm
0x373d0  ldarg.0
0x373d1  ldarg.2
0x373d2  ldarg.3
0x373d3  ldarg.s  4
0x373d5  call     instance void [System]System.ComponentModel.AsyncCompletedEventArgs::.ctor(class [mscorlib]System.Exception, bool, object)
0x373da  ldarg.0
0x373db  ldarg.1
0x373dc  stfld    object[] Microsoft.Crm.SdkTypeProxy.Metadata.ExecuteCompletedEventArgs::results
0x373e1  ret
```
