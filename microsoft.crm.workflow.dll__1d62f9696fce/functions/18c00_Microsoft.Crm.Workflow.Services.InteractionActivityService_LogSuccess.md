# Microsoft.Crm.Workflow.Services.InteractionActivityService::LogSuccess

- ea: `0x18c00`
- end: `0x18c81`
- name: `Microsoft.Crm.Workflow.Services.InteractionActivityService::LogSuccess`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x188b0`

## callees

- `0x6850`
- `0x9100`
- `0xdee0`
- `0xe0d0`
- `0x14770`
- `0x14840`
- `0x149c0`
- `0x18870`
- `0x18c00`

## pseudocode

```c

```

## disassembly

```asm
0x18c00  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x18c05  stloc.0
0x18c06  ldarg.0
0x18c07  ldarg.1
0x18c08  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x18c0d  call     instance string Microsoft.Crm.Workflow.Services.ActivityServiceBase::FindStepId(string stepIdAndDescription)
0x18c12  ldstr    aStep_0// "_step"
0x18c17  call     string [mscorlib]System.String::Concat(string, string)
0x18c1c  stloc.1
0x18c1d  ldarg.0
0x18c1e  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x18c23  callvirt instance class Microsoft.Crm.Workflow.WorkflowLogsProperty Microsoft.Crm.Workflow.ICommonWorkflowContext::get_WorkflowLogsProperty()
0x18c28  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Workflow.WorkflowLogsProperty::get_LogIds()
0x18c2d  ldloc.1
0x18c2e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x18c33  brfalse.s loc_18C4C
0x18c35  ldarg.0
0x18c36  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x18c3b  callvirt instance class Microsoft.Crm.Workflow.WorkflowLogsProperty Microsoft.Crm.Workflow.ICommonWorkflowContext::get_WorkflowLogsProperty()
0x18c40  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Workflow.WorkflowLogsProperty::get_LogIds()
0x18c45  ldloc.1
0x18c46  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::get_Item(void)
0x18c4b  stloc.0
0x18c4c  nop
0x18c4d  ldarg.0
0x18c4e  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.InteractionActivityService::get_InteractiveWorkflowInputContext()
0x18c53  callvirt instance class Microsoft.Crm.Workflow.PageResult Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::get_PageResult()
0x18c58  ldarg.2
0x18c59  callvirt instance void Microsoft.Crm.Workflow.PageResult::set_CurrentInteractionResult(string value)
0x18c5e  ldarg.0
0x18c5f  ldloc.0
0x18c60  ldc.i4.0
0x18c61  ldsfld   string [mscorlib]System.String::Empty
0x18c66  ldc.i4.2
0x18c67  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::UpdateLog(valuetype [mscorlib]System.Guid logId, int32 errorCode, string errorMessage, int32 status)
0x18c6c  leave.s  loc_18C80
0x18c6e  ldarg.0
0x18c6f  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.InteractionActivityService::get_InteractiveWorkflowInputContext()
0x18c74  callvirt instance class Microsoft.Crm.Workflow.PageResult Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::get_PageResult()
0x18c79  ldnull
0x18c7a  callvirt instance void Microsoft.Crm.Workflow.PageResult::set_CurrentInteractionResult(string value)
0x18c7f  endfinally
0x18c80  ret
```
