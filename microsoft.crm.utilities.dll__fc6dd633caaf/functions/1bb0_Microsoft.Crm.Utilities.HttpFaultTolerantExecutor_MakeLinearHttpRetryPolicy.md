# Microsoft.Crm.Utilities.HttpFaultTolerantExecutor::MakeLinearHttpRetryPolicy

- ea: `0x1bb0`
- end: `0x1bca`
- name: `Microsoft.Crm.Utilities.HttpFaultTolerantExecutor::MakeLinearHttpRetryPolicy`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1b10`

## pseudocode

```c

```

## disassembly

```asm
0x1bb0  ldc.i4.2
0x1bb1  ldc.r8   5.0
0x1bba  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1bbf  newobj   instance void [Microsoft.Practices.TransientFaultHandling.Core]Microsoft.Practices.TransientFaultHandling.FixedInterval::.ctor(int32, valuetype [mscorlib]System.TimeSpan)
0x1bc4  newobj   instance void class [Microsoft.Practices.TransientFaultHandling.Core]Microsoft.Practices.TransientFaultHandling.RetryPolicy`1<class TransientErrorDetectionStrategy>::.ctor(class [Microsoft.Practices.TransientFaultHandling.Core]Microsoft.Practices.TransientFaultHandling.RetryStrategy)
0x1bc9  ret
```
