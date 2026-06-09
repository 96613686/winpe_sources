# Microsoft.Crm.Workflow.Services.ConditionActivityService::ChildCompleted

- ea: `0x167c0`
- end: `0x168a4`
- name: `Microsoft.Crm.Workflow.Services.ConditionActivityService::ChildCompleted`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x9080`
- `0xf010`
- `0x167c0`
- `0x168b0`
- `0x16920`
- `0x2d630`

## pseudocode

```c

```

## disassembly

```asm
0x167c0  ldarg.2
0x167c1  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Wait()
0x167c6  ldarg.1
0x167c7  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<bool>::Get(!!T0)
0x167cc  stloc.0
0x167cd  ldarg.3
0x167ce  callvirt instance class [System.Activities]System.Activities.Activity [System.Activities]System.Activities.ActivityInstance::get_Activity()
0x167d3  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference
0x167d8  stloc.1
0x167d9  ldloc.1
0x167da  brfalse.s loc_167E4
0x167dc  ldloc.1
0x167dd  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference::get_AssemblyQualifiedName()
0x167e2  br.s     loc_167E9
0x167e4  ldsfld   string [mscorlib]System.String::Empty
0x167e9  stloc.2
0x167ea  ldloc.0
0x167eb  brfalse.s loc_1683B
0x167ed  ldarg.3
0x167ee  callvirt instance class [System.Activities]System.Activities.Activity [System.Activities]System.Activities.ActivityInstance::get_Activity()
0x167f3  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty
0x167f8  brfalse.s loc_1683B
0x167fa  ldarg.1
0x167fb  callvirt T0x2B000010
0x16800  stloc.3
0x16801  ldloc.3
0x16802  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WaitSubscription [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWaitNotificationService::get_SubscriptionToRegister()
0x16807  brfalse  loc_16898
0x1680c  ldloc.3
0x1680d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x16812  ldloc.3
0x16813  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WaitSubscription [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWaitNotificationService::get_SubscriptionToRegister()
0x16818  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WaitSubscription::get_EntityName()
0x1681d  ldloc.3
0x1681e  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WaitSubscription [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWaitNotificationService::get_SubscriptionToRegister()
0x16823  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WaitSubscription::get_EntityId()
0x16828  ldloc.3
0x16829  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WaitSubscription [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWaitNotificationService::get_SubscriptionToRegister()
0x1682e  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WaitSubscription::get_AttributeName()
0x16833  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWaitNotificationService::RegisterListener(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid, string)
0x16838  pop
0x16839  br.s     loc_16898
0x1683b  ldloc.2
0x1683c  ldtoken  Microsoft.Crm.Workflow.Activities.ConditionBranch
0x16841  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16846  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x1684b  call     bool Microsoft.Crm.Workflow.Utility.WorkflowUtility::CompareIgnoringVersion(string reference1, string reference2)
0x16850  brfalse.s loc_16898
0x16852  ldarg.0
0x16853  ldarg.1
0x16854  ldstr    aConditionbranc// "conditionBranchResult"
0x16859  call     T0x2B00000F
0x1685e  callvirt instance bool Microsoft.Crm.Workflow.ConditionBranchResultProperty::get_Result()
0x16863  stloc.s  4
0x16865  ldloc.0
0x16866  brfalse.s loc_1688C
0x16868  ldloc.s  4
0x1686a  brfalse.s loc_1688C
0x1686c  ldarg.1
0x1686d  callvirt T0x2B000010
0x16872  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWaitNotificationService::UnregisterAllListeners()
0x16877  ldarg.1
0x16878  callvirt instance void [System.Activities]System.Activities.NativeActivityContext::RemoveAllBookmarks()
0x1687d  ldarg.0
0x1687e  ldfld    bool Microsoft.Crm.Workflow.Services.ConditionActivityService::reEvaluateConditionCheck
0x16883  brfalse.s loc_1688C
0x16885  ldarg.0
0x16886  ldc.i4.0
0x16887  stfld    bool Microsoft.Crm.Workflow.Services.ConditionActivityService::reEvaluateConditionCheck
0x1688c  ldloc.s  4
0x1688e  brfalse.s loc_16898
0x16890  ldarg.0
0x16891  ldarg.2
0x16892  call     instance void Microsoft.Crm.Workflow.Services.ConditionActivityService::LogSuccess(class Microsoft.Crm.Workflow.Activities.ConditionSequence conditionSequence)
0x16897  ret
0x16898  ldarg.0
0x16899  ldarg.1
0x1689a  ldarg.3
0x1689b  ldarg.2
0x1689c  ldarg.s  4
0x1689e  call     instance void Microsoft.Crm.Workflow.Services.ConditionActivityService::ExecuteNextChild(class [System.Activities]System.Activities.NativeActivityContext executionContext, class [System.Activities]System.Activities.ActivityInstance completedInstance, class Microsoft.Crm.Workflow.Activities.ConditionSequence conditionSequence, class [System.Activities]System.Activities.Variable`1<int32> executionPointer)
0x168a3  ret
```
