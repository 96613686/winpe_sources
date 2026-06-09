# Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::SetTaskRunStatus

- ea: `0x5d0`
- end: `0x5df`
- name: `Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::SetTaskRunStatus`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x530`

## callees

- `0x640`
- `0x660`

## pseudocode

```c

```

## disassembly

```asm
0x5d0  ldarg.1
0x5d1  ldarg.2
0x5d2  callvirt instance void Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::set_taskRunStatusType(valuetype Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatusType value)
0x5d7  ldarg.1
0x5d8  ldarg.3
0x5d9  callvirt instance void Microsoft.Crm.Asynchronous.AnomalyDetectionTaskRunStatus::set_taskRunMessage(string value)
0x5de  ret
```
