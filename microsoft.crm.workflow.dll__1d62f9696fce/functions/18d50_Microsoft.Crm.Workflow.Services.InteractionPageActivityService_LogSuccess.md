# Microsoft.Crm.Workflow.Services.InteractionPageActivityService::LogSuccess

- ea: `0x18d50`
- end: `0x18dab`
- name: `Microsoft.Crm.Workflow.Services.InteractionPageActivityService::LogSuccess`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18db0`

## callees

- `0x6850`
- `0x9100`
- `0x14770`
- `0x14840`
- `0x149c0`
- `0x18d50`

## pseudocode

```c

```

## disassembly

```asm
0x18d50  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x18d55  stloc.0
0x18d56  ldarg.0
0x18d57  ldarg.1
0x18d58  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x18d5d  call     instance string Microsoft.Crm.Workflow.Services.ActivityServiceBase::FindStepId(string stepIdAndDescription)
0x18d62  ldstr    aStep_0// "_step"
0x18d67  call     string [mscorlib]System.String::Concat(string, string)
0x18d6c  stloc.1
0x18d6d  ldarg.0
0x18d6e  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x18d73  callvirt instance class Microsoft.Crm.Workflow.WorkflowLogsProperty Microsoft.Crm.Workflow.ICommonWorkflowContext::get_WorkflowLogsProperty()
0x18d78  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Workflow.WorkflowLogsProperty::get_LogIds()
0x18d7d  ldloc.1
0x18d7e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x18d83  brfalse.s loc_18D9C
0x18d85  ldarg.0
0x18d86  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x18d8b  callvirt instance class Microsoft.Crm.Workflow.WorkflowLogsProperty Microsoft.Crm.Workflow.ICommonWorkflowContext::get_WorkflowLogsProperty()
0x18d90  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Workflow.WorkflowLogsProperty::get_LogIds()
0x18d95  ldloc.1
0x18d96  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::get_Item(void)
0x18d9b  stloc.0
0x18d9c  ldarg.0
0x18d9d  ldloc.0
0x18d9e  ldc.i4.0
0x18d9f  ldsfld   string [mscorlib]System.String::Empty
0x18da4  ldc.i4.2
0x18da5  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::UpdateLog(valuetype [mscorlib]System.Guid logId, int32 errorCode, string errorMessage, int32 status)
0x18daa  ret
```
