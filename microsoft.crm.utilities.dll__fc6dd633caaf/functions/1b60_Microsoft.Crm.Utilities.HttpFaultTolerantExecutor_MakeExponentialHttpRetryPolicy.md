# Microsoft.Crm.Utilities.HttpFaultTolerantExecutor::MakeExponentialHttpRetryPolicy

- ea: `0x1b60`
- end: `0x1ba3`
- name: `Microsoft.Crm.Utilities.HttpFaultTolerantExecutor::MakeExponentialHttpRetryPolicy`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1b00`

## callees

- `0x1ec0`

## pseudocode

```c

```

## disassembly

```asm
0x1b60  newobj   instance void TransientErrorDetectionStrategy::.ctor()
0x1b65  ldc.r8   1.0
0x1b6e  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1b73  stloc.0
0x1b74  ldc.r8   10.0
0x1b7d  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1b82  stloc.1
0x1b83  ldc.r8   5.0
0x1b8c  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1b91  stloc.2
0x1b92  ldc.i4.3
0x1b93  ldloc.0
0x1b94  ldloc.1
0x1b95  ldloc.2
0x1b96  newobj   instance void [Microsoft.Practices.TransientFaultHandling.Core]Microsoft.Practices.TransientFaultHandling.ExponentialBackoff::.ctor(int32, valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1b9b  stloc.3
0x1b9c  ldloc.3
0x1b9d  newobj   instance void [Microsoft.Practices.TransientFaultHandling.Core]Microsoft.Practices.TransientFaultHandling.RetryPolicy::.ctor(class [Microsoft.Practices.TransientFaultHandling.Core]Microsoft.Practices.TransientFaultHandling.ITransientErrorDetectionStrategy, class [Microsoft.Practices.TransientFaultHandling.Core]Microsoft.Practices.TransientFaultHandling.RetryStrategy)
0x1ba2  ret
```
