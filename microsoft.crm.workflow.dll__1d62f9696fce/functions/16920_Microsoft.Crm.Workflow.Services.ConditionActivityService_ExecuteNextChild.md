# Microsoft.Crm.Workflow.Services.ConditionActivityService::ExecuteNextChild

- ea: `0x16920`
- end: `0x16a78`
- name: `Microsoft.Crm.Workflow.Services.ConditionActivityService::ExecuteNextChild`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x167c0`

## callees

- `0x9080`
- `0x14770`
- `0x165e0`
- `0x168b0`
- `0x16920`
- `0x2d5f0`
- `0x2d630`
- `0x2d650`
- `0x2d660`

## pseudocode

```c

```

## disassembly

```asm
0x16920  ldarg.s  4
0x16922  ldarg.1
0x16923  callvirt instance var<u1> class [System.Activities]System.Activities.Variable`1<int32>::Get(!!T0)
0x16928  stloc.0
0x16929  ldloc.0
0x1692a  ldarg.3
0x1692b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Activities()
0x16930  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x16935  bge.s    loc_1694B
0x16937  ldarg.3
0x16938  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Activities()
0x1693d  ldloc.0
0x1693e  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x16943  ldarg.2
0x16944  callvirt instance class [System.Activities]System.Activities.Activity [System.Activities]System.Activities.ActivityInstance::get_Activity()
0x16949  beq.s    loc_1695D
0x1694b  ldarg.3
0x1694c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Activities()
0x16951  ldarg.2
0x16952  callvirt instance class [System.Activities]System.Activities.Activity [System.Activities]System.Activities.ActivityInstance::get_Activity()
0x16957  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::IndexOf(var<u1>)
0x1695c  stloc.0
0x1695d  ldloc.0
0x1695e  ldc.i4.1
0x1695f  add
0x16960  stloc.0
0x16961  ldloc.0
0x16962  ldarg.3
0x16963  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Activities()
0x16968  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x1696d  beq.s    loc_169AD
0x1696f  ldarg.3
0x16970  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Activities()
0x16975  ldloc.0
0x16976  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x1697b  stloc.1
0x1697c  ldloc.1
0x1697d  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty
0x16982  stloc.2
0x16983  ldloc.2
0x16984  brfalse.s loc_16995
0x16986  ldarg.0
0x16987  ldfld    bool Microsoft.Crm.Workflow.Services.ConditionActivityService::reEvaluateConditionCheck
0x1698c  brfalse.s loc_16995
0x1698e  ldloc.2
0x1698f  ldc.i4.1
0x16990  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty::set_RefreshWorkflowConditionParameters(bool)
0x16995  ldarg.1
0x16996  ldloc.1
0x16997  ldarg.3
0x16998  callvirt instance class [System.Activities]System.Activities.CompletionCallback Microsoft.Crm.Workflow.Activities.ConditionSequence::get_OnChildComplete()
0x1699d  callvirt instance class [System.Activities]System.Activities.ActivityInstance [System.Activities]System.Activities.NativeActivityContext::ScheduleActivity(class [System.Activities]System.Activities.Activity, class [System.Activities]System.Activities.CompletionCallback)
0x169a2  pop
0x169a3  ldarg.s  4
0x169a5  ldarg.1
0x169a6  ldloc.0
0x169a7  callvirt instance void class [System.Activities]System.Activities.Variable`1<int32>::Set(class [System.Activities]System.Activities.ActivityContext, var<u1>)
0x169ac  ret
0x169ad  ldarg.3
0x169ae  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Wait()
0x169b3  ldarg.1
0x169b4  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<bool>::Get(!!T0)
0x169b9  stloc.3
0x169ba  ldarg.0
0x169bb  ldarg.1
0x169bc  ldstr    aConditionbranc// "conditionBranchResult"
0x169c1  call     T0x2B00000F
0x169c6  callvirt instance bool Microsoft.Crm.Workflow.ConditionBranchResultProperty::get_Result()
0x169cb  stloc.s  4
0x169cd  ldloc.3
0x169ce  brfalse  loc_16A6D
0x169d3  ldloc.s  4
0x169d5  brtrue   loc_16A6D
0x169da  ldarg.0
0x169db  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x169e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x169e5  stloc.s  5
0x169e7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x169ec  ldloc.s  5
0x169ee  ldloc.s  5
0x169f0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x169f5  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x169fa  ldstr    aActivateadditi// "ActivateAdditionalRefreshOfWorkflowCond"...
0x169ff  ldc.i4.0
0x16a00  box      [mscorlib]System.Boolean
0x16a05  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x16a0a  unbox.any [mscorlib]System.Boolean
0x16a0f  brfalse.s loc_16A54
0x16a11  ldarg.0
0x16a12  ldfld    bool Microsoft.Crm.Workflow.Services.ConditionActivityService::reEvaluateConditionCheck
0x16a17  brtrue.s loc_16A34
0x16a19  ldarg.0
0x16a1a  ldc.i4.1
0x16a1b  stfld    bool Microsoft.Crm.Workflow.Services.ConditionActivityService::reEvaluateConditionCheck
0x16a20  ldarg.s  4
0x16a22  ldarg.1
0x16a23  ldc.i4.0
0x16a24  callvirt instance void class [System.Activities]System.Activities.Variable`1<int32>::Set(class [System.Activities]System.Activities.ActivityContext, var<u1>)
0x16a29  ldarg.0
0x16a2a  ldarg.1
0x16a2b  ldarg.3
0x16a2c  ldarg.s  4
0x16a2e  call     instance void Microsoft.Crm.Workflow.Services.ConditionActivityService::Execute(class [System.Activities]System.Activities.NativeActivityContext executionContext, class Microsoft.Crm.Workflow.Activities.ConditionSequence conditionSequence, class [System.Activities]System.Activities.Variable`1<int32> executionPointer)
0x16a33  ret
0x16a34  ldarg.0
0x16a35  ldc.i4.0
0x16a36  stfld    bool Microsoft.Crm.Workflow.Services.ConditionActivityService::reEvaluateConditionCheck
0x16a3b  ldarg.1
0x16a3c  callvirt instance void [System.Activities]System.Activities.NativeActivityContext::RemoveAllBookmarks()
0x16a41  ldarg.1
0x16a42  call     string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.BookmarkNames::get_Default()
0x16a47  ldarg.3
0x16a48  callvirt instance class [System.Activities]System.Activities.BookmarkCallback Microsoft.Crm.Workflow.Activities.ConditionSequence::get_BookmarkCallback()
0x16a4d  callvirt instance class [System.Activities]System.Activities.Bookmark [System.Activities]System.Activities.NativeActivityContext::CreateBookmark(string, class [System.Activities]System.Activities.BookmarkCallback)
0x16a52  pop
0x16a53  ret
0x16a54  ldarg.1
0x16a55  callvirt instance void [System.Activities]System.Activities.NativeActivityContext::RemoveAllBookmarks()
0x16a5a  ldarg.1
0x16a5b  call     string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.BookmarkNames::get_Default()
0x16a60  ldarg.3
0x16a61  callvirt instance class [System.Activities]System.Activities.BookmarkCallback Microsoft.Crm.Workflow.Activities.ConditionSequence::get_BookmarkCallback()
0x16a66  callvirt instance class [System.Activities]System.Activities.Bookmark [System.Activities]System.Activities.NativeActivityContext::CreateBookmark(string, class [System.Activities]System.Activities.BookmarkCallback)
0x16a6b  pop
0x16a6c  ret
0x16a6d  ldloc.3
0x16a6e  brtrue.s loc_16A77
0x16a70  ldarg.0
0x16a71  ldarg.3
0x16a72  call     instance void Microsoft.Crm.Workflow.Services.ConditionActivityService::LogSuccess(class Microsoft.Crm.Workflow.Activities.ConditionSequence conditionSequence)
0x16a77  ret
```
