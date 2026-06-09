# Microsoft.Crm.Asynchronous.GoalRollupOperation::InitializeTreeEnumerator

- ea: `0xb310`
- end: `0xb3c5`
- name: `Microsoft.Crm.Asynchronous.GoalRollupOperation::InitializeTreeEnumerator`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xb240`

## string_xrefs

- `0xb363`: `amountdatatype`
- `0xb36b`: `isamount`

## pseudocode

```c

```

## disassembly

```asm
0xb310  ldarg.0
0xb311  ldarg.0
0xb312  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.GoalRollupOperation::_asyncEvent
0xb317  ldc.i4.1
0xb318  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.SdkServiceFactory::CreateInstance(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent, bool)
0xb31d  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.GoalRollupOperation::_orgService
0xb322  ldstr    aGoal// "goal"
0xb327  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0xb32c  stloc.0
0xb32d  ldloc.0
0xb32e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xb333  ldc.i4.7
0xb334  newarr   [mscorlib]System.String
0xb339  dup
0xb33a  ldc.i4.0
0xb33b  ldstr    aGoalid// "goalid"
0xb340  stelem.ref
0xb341  dup
0xb342  ldc.i4.1
0xb343  ldstr    aTreeid// "treeid"
0xb348  stelem.ref
0xb349  dup
0xb34a  ldc.i4.2
0xb34b  ldstr    aGoalstartdate// "goalstartdate"
0xb350  stelem.ref
0xb351  dup
0xb352  ldc.i4.3
0xb353  ldstr    aGoalenddate// "goalenddate"
0xb358  stelem.ref
0xb359  dup
0xb35a  ldc.i4.4
0xb35b  ldstr    aMetricid// "metricid"
0xb360  stelem.ref
0xb361  dup
0xb362  ldc.i4.5
0xb363  ldstr    aAmountdatatype// "amountdatatype"
0xb368  stelem.ref
0xb369  dup
0xb36a  ldc.i4.6
0xb36b  ldstr    aIsamount// "isamount"
0xb370  stelem.ref
0xb371  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0xb376  ldloc.0
0xb377  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xb37c  ldstr    aGoalenddate// "goalenddate"
0xb381  ldc.i4.4
0xb382  ldc.i4.1
0xb383  newarr   [mscorlib]System.Object
0xb388  dup
0xb389  ldc.i4.0
0xb38a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xb38f  stloc.1
0xb390  ldloca.s 1
0xb392  ldc.i4.m1
0xb393  ldarg.1
0xb394  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.GoalManagement.IRollupConfiguration::get_RollupExpiryTime()
0xb399  mul
0xb39a  conv.r8
0xb39b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xb3a0  box      [mscorlib]System.DateTime
0xb3a5  stelem.ref
0xb3a6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0xb3ab  ldloc.0
0xb3ac  ldc.i4.1
0xb3ad  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Distinct(bool)
0xb3b2  ldarg.0
0xb3b3  ldarg.0
0xb3b4  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.GoalRollupOperation::_orgService
0xb3b9  ldloc.0
0xb3ba  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.GoalManagement.PagedEntityEnumerator::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression)
0xb3bf  stfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.GoalManagement.PagedEntityEnumerator Microsoft.Crm.Asynchronous.GoalRollupOperation::_treeEnumerator
0xb3c4  ret
```
