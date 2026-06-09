# Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::.ctor

- ea: `0x4c0`
- end: `0x4e3`
- name: `Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::.ctor`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6e0`
- `0x8f0`

## callees

- `0x680`

## pseudocode

```c

```

## disassembly

```asm
0x4c0  ldarg.0
0x4c1  call     instance void [mscorlib]System.Object::.ctor()
0x4c6  ldarg.0
0x4c7  ldarg.1
0x4c8  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::_organizationId
0x4cd  ldarg.2
0x4ce  starg.s  2
0x4d0  ldarg.0
0x4d1  ldarg.2
0x4d2  ldc.i4.0
0x4d3  ldsfld   string [mscorlib]System.String::Empty
0x4d8  newobj   instance void Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::.ctor(string taskName, valuetype Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatusType taskRunStatusType, string taskRunMessage)
0x4dd  stfld    class Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::taskRunStatus
0x4e2  ret
```
