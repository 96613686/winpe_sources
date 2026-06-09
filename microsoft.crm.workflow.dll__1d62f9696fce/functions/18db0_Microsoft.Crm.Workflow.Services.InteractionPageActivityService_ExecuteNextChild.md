# Microsoft.Crm.Workflow.Services.InteractionPageActivityService::ExecuteNextChild

- ea: `0x18db0`
- end: `0x18f82`
- name: `Microsoft.Crm.Workflow.Services.InteractionPageActivityService::ExecuteNextChild`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18d40`

## callees

- `0xdf40`
- `0xdf50`
- `0xdfe0`
- `0xe930`
- `0xe950`
- `0xe970`
- `0x14770`
- `0x14820`
- `0x18cc0`
- `0x18ce0`
- `0x18d50`
- `0x18db0`
- `0x2e040`
- `0x2e060`
- `0x2e0a0`
- `0x2e0b0`

## string_xrefs

- `0x18eb1`: `ExecuteNextChild: Created bookmark to get response at Page '{0}', for interactive workflow '{1}'.`
- `0x18f4b`: `ExecuteNextChild: Completed bookmark resume processing for interactive workflow '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x18db0  ldarg.s  4
0x18db2  ldarg.1
0x18db3  callvirt instance var<u1> class [System.Activities]System.Activities.Variable`1<int32>::Get(!!T0)
0x18db8  stloc.0
0x18db9  ldloc.0
0x18dba  ldc.i4.1
0x18dbb  add
0x18dbc  stloc.0
0x18dbd  ldc.i4.0
0x18dbe  stloc.1
0x18dbf  ldloc.0
0x18dc0  ldarg.3
0x18dc1  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.InteractionPage::get_Activities()
0x18dc6  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x18dcb  bge      loc_18F13
0x18dd0  ldarg.3
0x18dd1  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.InteractionPage::get_Activities()
0x18dd6  ldloc.0
0x18dd7  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x18ddc  stloc.2
0x18ddd  ldarg.0
0x18dde  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext Microsoft.Crm.Workflow.Services.InteractionPageActivityService::get_InteractiveWorkflowOutputContext()
0x18de3  callvirt instance class Microsoft.Crm.Workflow.PageUIDetail Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext::get_PageUIDetail()
0x18de8  ldarg.0
0x18de9  ldarg.3
0x18dea  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x18def  call     instance string Microsoft.Crm.Workflow.Services.ActivityServiceBase::FindStepDescription(string stepIdAndDescription)
0x18df4  callvirt instance void Microsoft.Crm.Workflow.PageUIDetail::set_Description(string value)
0x18df9  ldarg.0
0x18dfa  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.InteractionPageActivityService::get_InteractiveWorkflowInputContext()
0x18dff  callvirt instance bool Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::get_UnderResumeBookmarkProcessing()
0x18e04  brtrue.s loc_18E5B
0x18e06  ldloc.2
0x18e07  ldarg.2
0x18e08  callvirt instance class [System.Activities]System.Activities.Activity [System.Activities]System.Activities.ActivityInstance::get_Activity()
0x18e0d  beq.s    loc_18E5B
0x18e0f  ldarg.2
0x18e10  callvirt instance class [System.Activities]System.Activities.Activity [System.Activities]System.Activities.ActivityInstance::get_Activity()
0x18e15  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x18e1a  ldtoken  [System.Activities]System.Activities.Statements.Sequence
0x18e1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18e24  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x18e29  brfalse.s loc_18E5B
0x18e2b  ldarg.2
0x18e2c  callvirt instance class [System.Activities]System.Activities.Activity [System.Activities]System.Activities.ActivityInstance::get_Activity()
0x18e31  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x18e36  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::InteractionStepActivityNamePrefix
0x18e3b  callvirt instance bool [mscorlib]System.String::Contains(string)
0x18e40  brfalse.s loc_18E5B
0x18e42  ldloc.2
0x18e43  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x18e48  ldtoken  class [System.Activities]System.Activities.Statements.Assign`1<class Microsoft.Crm.Workflow.InteractionActivityResult>
0x18e4d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x18e52  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x18e57  brfalse.s loc_18E5B
0x18e59  ldc.i4.1
0x18e5a  stloc.1
0x18e5b  ldloc.1
0x18e5c  brfalse  loc_18EFB
0x18e61  ldarg.s  4
0x18e63  ldarg.1
0x18e64  ldloc.0
0x18e65  callvirt instance void class [System.Activities]System.Activities.Variable`1<int32>::Set(class [System.Activities]System.Activities.ActivityContext, var<u1>)
0x18e6a  ldarg.3
0x18e6b  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.InteractionPage::get_AllowBack()
0x18e70  ldarg.1
0x18e71  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<bool>::Get(!!T0)
0x18e76  stloc.3
0x18e77  ldarg.0
0x18e78  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext Microsoft.Crm.Workflow.Services.InteractionPageActivityService::get_InteractiveWorkflowOutputContext()
0x18e7d  callvirt instance class Microsoft.Crm.Workflow.PageUIDetail Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext::get_PageUIDetail()
0x18e82  ldloc.3
0x18e83  callvirt instance void Microsoft.Crm.Workflow.PageUIDetail::set_AllowBack(bool value)
0x18e88  ldarg.0
0x18e89  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext Microsoft.Crm.Workflow.Services.InteractionPageActivityService::get_InteractiveWorkflowOutputContext()
0x18e8e  callvirt instance class Microsoft.Crm.Workflow.PageUIDetail Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext::get_PageUIDetail()
0x18e93  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityDetail> Microsoft.Crm.Workflow.PageUIDetail::get_InteractionActivitiesDetails()
0x18e98  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityDetail>::get_Count()
0x18e9d  ldc.i4.0
0x18e9e  cgt
0x18ea0  ldstr    aInteractionpag_0// "InteractionPage should have at least on"...
0x18ea5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x18eaa  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x18eaf  ldc.i4.s 0x1E
0x18eb1  ldstr    aExecutenextchi// "ExecuteNextChild: Created bookmark to g"...
0x18eb6  ldc.i4.2
0x18eb7  newarr   [mscorlib]System.Object
0x18ebc  dup
0x18ebd  ldc.i4.0
0x18ebe  ldarg.2
0x18ebf  callvirt instance class [System.Activities]System.Activities.Activity [System.Activities]System.Activities.ActivityInstance::get_Activity()
0x18ec4  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x18ec9  stelem.ref
0x18eca  dup
0x18ecb  ldc.i4.1
0x18ecc  ldarg.0
0x18ecd  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x18ed2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x18ed7  box      [mscorlib]System.Guid
0x18edc  stelem.ref
0x18edd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18ee2  ldarg.1
0x18ee3  callvirt instance void [System.Activities]System.Activities.NativeActivityContext::RemoveAllBookmarks()
0x18ee8  ldarg.1
0x18ee9  call     string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.BookmarkNames::get_Default()
0x18eee  ldarg.3
0x18eef  callvirt instance class [System.Activities]System.Activities.BookmarkCallback Microsoft.Crm.Workflow.Activities.InteractionPage::get_BookmarkCallback()
0x18ef4  callvirt instance class [System.Activities]System.Activities.Bookmark [System.Activities]System.Activities.NativeActivityContext::CreateBookmark(string, class [System.Activities]System.Activities.BookmarkCallback)
0x18ef9  pop
0x18efa  ret
0x18efb  ldarg.1
0x18efc  ldloc.2
0x18efd  ldarg.3
0x18efe  callvirt instance class [System.Activities]System.Activities.CompletionCallback Microsoft.Crm.Workflow.Activities.InteractionPage::get_OnChildComplete()
0x18f03  callvirt instance class [System.Activities]System.Activities.ActivityInstance [System.Activities]System.Activities.NativeActivityContext::ScheduleActivity(class [System.Activities]System.Activities.Activity, class [System.Activities]System.Activities.CompletionCallback)
0x18f08  pop
0x18f09  ldarg.s  4
0x18f0b  ldarg.1
0x18f0c  ldloc.0
0x18f0d  callvirt instance void class [System.Activities]System.Activities.Variable`1<int32>::Set(class [System.Activities]System.Activities.ActivityContext, var<u1>)
0x18f12  ret
0x18f13  ldarg.0
0x18f14  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.InteractionPageActivityService::get_InteractiveWorkflowInputContext()
0x18f19  callvirt instance bool Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::get_UnderResumeBookmarkProcessing()
0x18f1e  brtrue.s loc_18F44
0x18f20  ldarg.0
0x18f21  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext Microsoft.Crm.Workflow.Services.InteractionPageActivityService::get_InteractiveWorkflowOutputContext()
0x18f26  callvirt instance class Microsoft.Crm.Workflow.PageUIDetail Microsoft.Crm.Workflow.InteractiveWorkflowOutputContext::get_PageUIDetail()
0x18f2b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityDetail> Microsoft.Crm.Workflow.PageUIDetail::get_InteractionActivitiesDetails()
0x18f30  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Workflow.InteractionActivityDetail>::get_Count()
0x18f35  ldc.i4.0
0x18f36  cgt
0x18f38  ldstr    aInteractionpag_0// "InteractionPage should have at least on"...
0x18f3d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x18f42  br.s     loc_18F6E
0x18f44  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x18f49  ldc.i4.s 0x1E
0x18f4b  ldstr    aExecutenextchi_0// "ExecuteNextChild: Completed bookmark re"...
0x18f50  ldc.i4.1
0x18f51  newarr   [mscorlib]System.Object
0x18f56  dup
0x18f57  ldc.i4.0
0x18f58  ldarg.0
0x18f59  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x18f5e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0x18f63  box      [mscorlib]System.Guid
0x18f68  stelem.ref
0x18f69  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18f6e  ldarg.0
0x18f6f  call     instance class Microsoft.Crm.Workflow.InteractiveWorkflowInputContext Microsoft.Crm.Workflow.Services.InteractionPageActivityService::get_InteractiveWorkflowInputContext()
0x18f74  ldc.i4.0
0x18f75  callvirt instance void Microsoft.Crm.Workflow.InteractiveWorkflowInputContext::set_UnderResumeBookmarkProcessing(bool value)
0x18f7a  ldarg.0
0x18f7b  ldarg.3
0x18f7c  call     instance void Microsoft.Crm.Workflow.Services.InteractionPageActivityService::LogSuccess(class Microsoft.Crm.Workflow.Activities.InteractionPage interactionPage)
0x18f81  ret
```
