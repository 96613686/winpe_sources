# Microsoft.Crm.Workflow.Services.ExpressionServiceBase::Delay

- ea: `0x17ff0`
- end: `0x18081`
- name: `Microsoft.Crm.Workflow.Services.ExpressionServiceBase::Delay`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x68e0`
- `0x8b90`
- `0x8ba0`
- `0x14770`
- `0x17ff0`

## pseudocode

```c

```

## disassembly

```asm
0x17ff0  ldarg.2
0x17ff1  callvirt instance class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.DateTime> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.Postpone::get_PostponeUntil()
0x17ff6  ldarg.1
0x17ff7  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<valuetype [mscorlib]System.DateTime>::Get(!!T0)
0x17ffc  stloc.0
0x17ffd  ldloca.s 0
0x17fff  call     instance valuetype [mscorlib]System.DateTimeKind [mscorlib]System.DateTime::get_Kind()
0x18004  ldc.i4.2
0x18005  bne.un.s loc_1800F
0x18007  ldloca.s 0
0x18009  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x1800e  stloc.0
0x1800f  ldloc.0
0x18010  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x18015  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1801a  brfalse.s loc_18022
0x1801c  call     valuetype [mscorlib]System.DateTime [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.DateTimeAttributeMetadata::get_MaxSupportedValue()
0x18021  stloc.0
0x18022  ldarg.2
0x18023  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.Postpone::get_BlockExecution()
0x18028  ldarg.1
0x18029  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<bool>::Get(!!T0)
0x1802e  ldarg.0
0x1802f  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x18034  callvirt instance class Microsoft.Crm.Workflow.WorkflowInstanceStateBase Microsoft.Crm.Workflow.ICommonWorkflowContext::get_InstanceState()
0x18039  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_PostponeUntil()
0x1803e  stloc.1
0x1803f  ldloc.1
0x18040  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x18045  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1804a  brtrue.s loc_18055
0x1804c  ldloc.1
0x1804d  ldloc.0
0x1804e  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x18053  brfalse.s loc_18066
0x18055  ldarg.0
0x18056  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x1805b  callvirt instance class Microsoft.Crm.Workflow.WorkflowInstanceStateBase Microsoft.Crm.Workflow.ICommonWorkflowContext::get_InstanceState()
0x18060  ldloc.0
0x18061  callvirt instance void Microsoft.Crm.Workflow.WorkflowInstanceStateBase::set_PostponeUntil(valuetype [mscorlib]System.DateTime value)
0x18066  brfalse.s loc_18080
0x18068  ldarg.1
0x18069  callvirt instance void [System.Activities]System.Activities.NativeActivityContext::RemoveAllBookmarks()
0x1806e  ldarg.1
0x1806f  call     string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.BookmarkNames::get_Default()
0x18074  ldarg.2
0x18075  callvirt instance class [System.Activities]System.Activities.BookmarkCallback [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.Postpone::get_BookmarkCallback()
0x1807a  callvirt instance class [System.Activities]System.Activities.Bookmark [System.Activities]System.Activities.NativeActivityContext::CreateBookmark(string, class [System.Activities]System.Activities.BookmarkCallback)
0x1807f  pop
0x18080  ret
```
