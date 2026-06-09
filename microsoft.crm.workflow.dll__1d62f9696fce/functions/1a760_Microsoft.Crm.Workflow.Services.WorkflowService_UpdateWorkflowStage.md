# Microsoft.Crm.Workflow.Services.WorkflowService::UpdateWorkflowStage

- ea: `0x1a760`
- end: `0x1a7b5`
- name: `Microsoft.Crm.Workflow.Services.WorkflowService::UpdateWorkflowStage`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1a650`
- `0x1a6d0`

## callees

- `0x6b00`
- `0x90c0`
- `0x1a530`
- `0x1a760`

## pseudocode

```c

```

## disassembly

```asm
0x1a760  ldarg.0
0x1a761  ldarg.1
0x1a762  ldstr    aStagestep// "StageStep"
0x1a767  call     instance bool Microsoft.Crm.Workflow.Services.WorkflowService::IsStepOfType(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference activityReference, string stepType)
0x1a76c  brfalse.s loc_1A7B4
0x1a76e  ldarg.1
0x1a76f  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x1a774  stloc.0
0x1a775  ldloc.0
0x1a776  ldc.i4.s 0x3A
0x1a778  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x1a77d  stloc.1
0x1a77e  ldloc.1
0x1a77f  ldc.i4.m1
0x1a780  beq.s    loc_1A78C
0x1a782  ldloc.0
0x1a783  ldloc.1
0x1a784  ldc.i4.2
0x1a785  add
0x1a786  callvirt instance string [mscorlib]System.String::Substring(int32)
0x1a78b  stloc.0
0x1a78c  ldarg.0
0x1a78d  ldarg.2
0x1a78e  ldtoken  Microsoft.Crm.Workflow.WorkflowStageProperty
0x1a793  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a798  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1a79d  call     T0x2B00000A
0x1a7a2  ldloc.0
0x1a7a3  callvirt instance void Microsoft.Crm.Workflow.WorkflowStageProperty::set_Stage(string value)
0x1a7a8  ldarg.2
0x1a7a9  callvirt T0x2B000009
0x1a7ae  ldloc.0
0x1a7af  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::SetStageName(string stageName)
0x1a7b4  ret
```
