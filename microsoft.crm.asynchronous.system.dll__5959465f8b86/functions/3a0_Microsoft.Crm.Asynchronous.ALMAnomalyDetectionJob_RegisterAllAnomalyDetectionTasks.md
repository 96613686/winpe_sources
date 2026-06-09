# Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::RegisterAllAnomalyDetectionTasks

- ea: `0x3a0`
- end: `0x3cd`
- name: `Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::RegisterAllAnomalyDetectionTasks`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x380`

## callees

- `0x6e0`
- `0x8f0`

## pseudocode

```c

```

## disassembly

```asm
0x3a0  ldarg.0
0x3a1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IALMAnomalyDetectionTask> Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::_taskList
0x3a6  ldarg.0
0x3a7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::_organizationId
0x3ac  newobj   instance void Microsoft.Crm.Asynchronous.ALMSchemaMetadataDiscrepancyTask::.ctor(valuetype [mscorlib]System.Guid organizationId)
0x3b1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IALMAnomalyDetectionTask>::Add(var<u1>)
0x3b6  ldarg.0
0x3b7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IALMAnomalyDetectionTask> Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::_taskList
0x3bc  ldarg.0
0x3bd  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionJob::_organizationId
0x3c2  newobj   instance void Microsoft.Crm.Asynchronous.ALMRollupJobTableLimitDetectionTask::.ctor(valuetype [mscorlib]System.Guid organizationId)
0x3c7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IALMAnomalyDetectionTask>::Add(var<u1>)
0x3cc  ret
```
