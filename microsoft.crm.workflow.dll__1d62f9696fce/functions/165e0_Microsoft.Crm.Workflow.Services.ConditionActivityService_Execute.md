# Microsoft.Crm.Workflow.Services.ConditionActivityService::Execute

- ea: `0x165e0`
- end: `0x1668e`
- name: `Microsoft.Crm.Workflow.Services.ConditionActivityService::Execute`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x16920`
- `0x16a80`

## callees

- `0x9070`
- `0x148a0`
- `0x14930`
- `0x165e0`
- `0x16690`
- `0x16770`
- `0x2d5f0`
- `0x2d650`

## pseudocode

```c

```

## disassembly

```asm
0x165e0  ldarg.0
0x165e1  ldarg.2
0x165e2  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog(class [System.Activities]System.Activities.Activity activity)
0x165e7  stloc.0
0x165e8  ldarg.0
0x165e9  ldarg.3
0x165ea  ldarg.1
0x165eb  ldarg.2
0x165ec  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x165f1  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetExecutionPointer(class [System.Activities]System.Activities.Variable`1<int32> executionPointer, class [System.Activities]System.Activities.ActivityContext executionContext, string displayName)
0x165f6  brfalse.s loc_16601
0x165f8  ldarg.0
0x165f9  ldarg.1
0x165fa  ldarg.3
0x165fb  ldarg.2
0x165fc  call     instance void Microsoft.Crm.Workflow.Services.ConditionActivityService::SetConditionToTrue(class [System.Activities]System.Activities.NativeActivityContext executionContext, class [System.Activities]System.Activities.Variable`1<int32> executionPointer, class Microsoft.Crm.Workflow.Activities.ConditionSequence conditionSequence)
0x16601  ldarg.1
0x16602  callvirt instance class [System.Activities]System.Activities.ExecutionProperties [System.Activities]System.Activities.NativeActivityContext::get_Properties()
0x16607  ldstr    aConditionbranc// "conditionBranchResult"
0x1660c  callvirt instance bool [System.Activities]System.Activities.ExecutionProperties::Remove(string)
0x16611  pop
0x16612  ldarg.1
0x16613  callvirt instance class [System.Activities]System.Activities.ExecutionProperties [System.Activities]System.Activities.NativeActivityContext::get_Properties()
0x16618  ldstr    aConditionbranc// "conditionBranchResult"
0x1661d  ldc.i4.0
0x1661e  newobj   instance void Microsoft.Crm.Workflow.ConditionBranchResultProperty::.ctor(bool result)
0x16623  callvirt instance void [System.Activities]System.Activities.ExecutionProperties::Add(string, object)
0x16628  ldarg.0
0x16629  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Workflow.Services.ConditionActivityService::_logDictionary
0x1662e  ldarg.2
0x1662f  callvirt instance string [System.Activities]System.Activities.Activity::get_Id()
0x16634  ldloc.0
0x16635  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::set_Item(var<u1>, !!T0)
0x1663a  ldarg.3
0x1663b  ldarg.1
0x1663c  callvirt instance var<u1> class [System.Activities]System.Activities.Variable`1<int32>::Get(!!T0)
0x16641  stloc.1
0x16642  ldloc.1
0x16643  ldarg.2
0x16644  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Activities()
0x16649  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x1664e  bge.s    loc_1668D
0x16650  ldarg.2
0x16651  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.ConditionSequence::get_Activities()
0x16656  ldloc.1
0x16657  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x1665c  stloc.2
0x1665d  ldloc.2
0x1665e  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty
0x16663  stloc.3
0x16664  ldloc.3
0x16665  brfalse.s loc_1667F
0x16667  ldarg.0
0x16668  ldfld    bool Microsoft.Crm.Workflow.Services.ConditionActivityService::reEvaluateConditionCheck
0x1666d  brtrue.s loc_16678
0x1666f  ldarg.0
0x16670  ldloc.3
0x16671  call     instance bool Microsoft.Crm.Workflow.Services.ConditionActivityService::IsEntityReferenceArgument(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty activity)
0x16676  brfalse.s loc_1667F
0x16678  ldloc.3
0x16679  ldc.i4.1
0x1667a  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.GetEntityProperty::set_RefreshWorkflowConditionParameters(bool)
0x1667f  ldarg.1
0x16680  ldloc.2
0x16681  ldarg.2
0x16682  callvirt instance class [System.Activities]System.Activities.CompletionCallback Microsoft.Crm.Workflow.Activities.ConditionSequence::get_OnChildComplete()
0x16687  callvirt instance class [System.Activities]System.Activities.ActivityInstance [System.Activities]System.Activities.NativeActivityContext::ScheduleActivity(class [System.Activities]System.Activities.Activity, class [System.Activities]System.Activities.CompletionCallback)
0x1668c  pop
0x1668d  ret
```
