# Microsoft.Crm.SdkTypeProxy.CreateCompletedEventArgs::.ctor

- ea: `0x35ef0`
- end: `0x35f02`
- name: `Microsoft.Crm.SdkTypeProxy.CreateCompletedEventArgs::.ctor`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x520`

## pseudocode

```c

```

## disassembly

```asm
0x35ef0  ldarg.0
0x35ef1  ldarg.2
0x35ef2  ldarg.3
0x35ef3  ldarg.s  4
0x35ef5  call     instance void [System]System.ComponentModel.AsyncCompletedEventArgs::.ctor(class [mscorlib]System.Exception, bool, object)
0x35efa  ldarg.0
0x35efb  ldarg.1
0x35efc  stfld    object[] Microsoft.Crm.SdkTypeProxy.CreateCompletedEventArgs::results
0x35f01  ret
```
