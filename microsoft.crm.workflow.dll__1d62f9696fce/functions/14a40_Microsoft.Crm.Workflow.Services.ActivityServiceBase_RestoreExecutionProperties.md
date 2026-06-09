# Microsoft.Crm.Workflow.Services.ActivityServiceBase::RestoreExecutionProperties

- ea: `0x14a40`
- end: `0x14ac3`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::RestoreExecutionProperties`
- size: `131`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x16a80`
- `0x18220`
- `0x18f90`

## callees

- `0x6840`
- `0x6860`
- `0x68a0`
- `0x6970`
- `0x6990`
- `0x69b0`

## string_xrefs

- `0x14a94`: `WorkflowAutoDeleteSet`

## pseudocode

```c

```

## disassembly

```asm
0x14a40  ldarg.1
0x14a41  callvirt T0x2B000009
0x14a46  dup
0x14a47  ldarg.0
0x14a48  ldarg.1
0x14a49  ldtoken  Microsoft.Crm.Workflow.WorkflowStageProperty
0x14a4e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14a53  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x14a58  call     T0x2B00000A
0x14a5d  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::set_WorkflowStageProperty(class Microsoft.Crm.Workflow.WorkflowStageProperty value)
0x14a62  dup
0x14a63  ldarg.0
0x14a64  ldarg.1
0x14a65  ldtoken  Microsoft.Crm.Workflow.WorkflowLogsProperty
0x14a6a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14a6f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x14a74  call     T0x2B00000B
0x14a79  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::set_WorkflowLogsProperty(class Microsoft.Crm.Workflow.WorkflowLogsProperty value)
0x14a7e  dup
0x14a7f  ldarg.0
0x14a80  ldarg.1
0x14a81  ldstr    aWorkflowloggin// "WorkflowLoggingEnabled"
0x14a86  ldc.i4.1
0x14a87  call     T0x2B00000C
0x14a8c  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::set_IsLoggingEnabled(bool value)
0x14a91  dup
0x14a92  ldarg.0
0x14a93  ldarg.1
0x14a94  ldstr    aWorkflowautode// "WorkflowAutoDeleteSet"
0x14a99  ldc.i4.0
0x14a9a  call     T0x2B00000C
0x14a9f  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::set_IsAutoDeleteSet(bool value)
0x14aa4  dup
0x14aa5  ldarg.0
0x14aa6  ldarg.1
0x14aa7  ldstr    aIscrmuiworkflo_0// "IsCrmUIWorkflow"
0x14aac  ldc.i4.0
0x14aad  call     T0x2B00000C
0x14ab2  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::set_IsCrmUIWorkflow(bool value)
0x14ab7  ldarg.1
0x14ab8  callvirt T0x2B00000D
0x14abd  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::set_WorkflowTracingService(class Microsoft.Crm.Workflow.WorkflowTracingService value)
0x14ac2  ret
```
