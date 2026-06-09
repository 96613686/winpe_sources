# Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetStepRegardingRecord_0

- ea: `0x147a0`
- end: `0x147ba`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetStepRegardingRecord_0`
- size: `26`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14790`
- `0x2e8b0`
- `0x2e9a0`

## callees

- `0x68d0`
- `0x69d0`
- `0x14770`

## pseudocode

```c

```

## disassembly

```asm
0x147a0  ldarg.0
0x147a1  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x147a6  ldarg.3
0x147a7  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::set_ChildWorkflowInstanceId(valuetype [mscorlib]System.Guid value)
0x147ac  ldarg.0
0x147ad  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x147b2  ldarg.1
0x147b3  ldarg.2
0x147b4  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::SetStepRegardingRecord(string entityName, valuetype [mscorlib]System.Guid entityId)
0x147b9  ret
```
