# Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::.ctor

- ea: `0x680`
- end: `0x6b2`
- name: `Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::.ctor`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x4c0`

## pseudocode

```c

```

## disassembly

```asm
0x680  ldarg.0
0x681  ldsfld   string [mscorlib]System.String::Empty
0x686  stfld    string Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::_taskRunMessage
0x68b  ldarg.0
0x68c  ldsfld   string [mscorlib]System.String::Empty
0x691  stfld    string Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::_taskName
0x696  ldarg.0
0x697  call     instance void [mscorlib]System.Object::.ctor()
0x69c  ldarg.0
0x69d  ldarg.2
0x69e  stfld    valuetype Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatusType Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::_taskRunStatusType
0x6a3  ldarg.0
0x6a4  ldarg.3
0x6a5  stfld    string Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::_taskRunMessage
0x6aa  ldarg.0
0x6ab  ldarg.1
0x6ac  stfld    string Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::_taskName
0x6b1  ret
```
