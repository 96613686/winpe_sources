# Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetStepRegardingRecord

- ea: `0x14790`
- end: `0x1479e`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetStepRegardingRecord`
- size: `14`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18a80`
- `0x2e7c0`
- `0x2ea90`
- `0x2ed90`
- `0x2ee70`
- `0x2f0e0`
- `0x2f190`

## callees

- `0x147a0`

## pseudocode

```c

```

## disassembly

```asm
0x14790  ldarg.0
0x14791  ldarg.1
0x14792  ldarg.2
0x14793  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14798  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetStepRegardingRecord(string entityName, valuetype [mscorlib]System.Guid entityId, valuetype [mscorlib]System.Guid childWorkflowInstanceId)
0x1479d  ret
```
