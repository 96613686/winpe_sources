# Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::.ctor

- ea: `0x8f0`
- end: `0x909`
- name: `Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::.ctor`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3a0`

## callees

- `0x4c0`

## string_xrefs

- `0x8fe`: `ALMRollupJobTableLimitDetectionTask`

## pseudocode

```c

```

## disassembly

```asm
0x8f0  ldarg.0
0x8f1  ldc.i4   0x186A0
0x8f6  conv.i8
0x8f7  stfld    int64 Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::RollupJobBaseThreshold
0x8fc  ldarg.0
0x8fd  ldarg.1
0x8fe  ldstr    aAlmrollupjobta// "ALMRollupJobTableLimitDetectionTask"
0x903  call     instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::.ctor(valuetype [mscorlib]System.Guid organizationId, string taskName)
0x908  ret
```
