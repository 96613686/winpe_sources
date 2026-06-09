# Microsoft.Crm.Asynchronous.AsyncServiceConnectionRetryPolicy::.ctor

- ea: `0x1ea0`
- end: `0x1ebc`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceConnectionRetryPolicy::.ctor`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe20`

## callees

- `0x1ea0`

## pseudocode

```c

```

## disassembly

```asm
0x1ea0  ldarg.0
0x1ea1  call     instance void [mscorlib]System.Object::.ctor()
0x1ea6  ldarg.1
0x1ea7  brtrue.s loc_1EB4
0x1ea9  ldstr    aRetrystrategy// "retryStrategy"
0x1eae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1eb3  throw
0x1eb4  ldarg.0
0x1eb5  ldarg.1
0x1eb6  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ITransientErrorDetectionStrategy Microsoft.Crm.Asynchronous.AsyncServiceConnectionRetryPolicy::retryStrategy
0x1ebb  ret
```
