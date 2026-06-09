# Microsoft.Crm.Platform.Server.SelectionAlgorithmService::RetrieveDefaultProcessInstanceFallback

- ea: `0x50250`
- end: `0x503b7`
- name: `Microsoft.Crm.Platform.Server.SelectionAlgorithmService::RetrieveDefaultProcessInstanceFallback`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x4ffa0`

## callees

- `0x13b10`
- `0x18520`
- `0x18540`
- `0x18800`
- `0x1a9c0`
- `0x1ab00`
- `0x1ab20`
- `0x1ae30`
- `0x1afa0`
- `0x4cfe0`
- `0x4d020`
- `0x4df40`
- `0x50250`
- `0x58f50`
- `0x78330`
- `0x89c80`

## string_xrefs

- `0x5031a`: `processid`
- `0x5033d`: `traversedpath`

## pseudocode

```c

```

## disassembly

```asm
0x50250  newobj   instance void <>c__DisplayClass19_0::.ctor()
0x50255  stloc.0
0x50256  ldloc.0
0x50257  ldarg.0
0x50258  stfld    class Microsoft.Crm.Platform.Server.SelectionAlgorithmService <>c__DisplayClass19_0::<>4__this
0x5025d  ldloc.0
0x5025e  ldarg.s  4
0x50260  stfld    class Microsoft.Crm.Platform.Server.IExecutionContext <>c__DisplayClass19_0::executionContext
0x50265  ldc.i4.5
0x50266  newarr   Microsoft.Crm.Query.FilterExpression
0x5026b  stloc.1
0x5026c  ldstr    aBusinessproces// "BusinessProcessFlowInstance"
0x50271  ldloc.0
0x50272  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext <>c__DisplayClass19_0::executionContext
0x50277  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x5027c  stloc.2
0x5027d  ldloc.2
0x5027e  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x50283  ldc.i4.1
0x50284  callvirt instance void Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator value)
0x50289  ldloc.2
0x5028a  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5028f  ldstr    aUnion// "union"
0x50294  callvirt instance void Microsoft.Crm.Query.FilterExpression::set_FilterHint(string value)
0x50299  ldc.i4.0
0x5029a  stloc.s  4
0x5029c  br.s     loc_502FF
0x5029e  ldloc.1
0x5029f  ldloc.s  4
0x502a1  ldstr    aBusinessproces// "BusinessProcessFlowInstance"
0x502a6  ldloc.0
0x502a7  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext <>c__DisplayClass19_0::executionContext
0x502ac  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x502b1  stelem.ref
0x502b2  ldloc.s  4
0x502b4  call     string Microsoft.Crm.Platform.Server.BusinessProcessFlowEntityMapUtility::GetAttributeNameForEntityId(valuetype Microsoft.Crm.Platform.Server.EntityPosition entityPosition)
0x502b9  stloc.s  5
0x502bb  ldloc.s  4
0x502bd  call     string Microsoft.Crm.Platform.Server.BusinessProcessFlowEntityMapUtility::GetAttributeNameForEntityOtc(valuetype Microsoft.Crm.Platform.Server.EntityPosition entityPosition)
0x502c2  stloc.s  6
0x502c4  ldloc.1
0x502c5  ldloc.s  4
0x502c7  ldelem.ref
0x502c8  ldloc.s  5
0x502ca  ldc.i4.0
0x502cb  ldarg.1
0x502cc  box      [mscorlib]System.Guid
0x502d1  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x502d6  pop
0x502d7  ldloc.1
0x502d8  ldloc.s  4
0x502da  ldelem.ref
0x502db  ldloc.s  6
0x502dd  ldc.i4.0
0x502de  ldarg.2
0x502df  box      [mscorlib]System.Int32
0x502e4  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x502e9  pop
0x502ea  ldloc.2
0x502eb  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x502f0  ldloc.1
0x502f1  ldloc.s  4
0x502f3  ldelem.ref
0x502f4  callvirt instance void Microsoft.Crm.Query.FilterExpression::AddFilter(class Microsoft.Crm.Query.FilterExpression childFilter)
0x502f9  ldloc.s  4
0x502fb  ldc.i4.1
0x502fc  add
0x502fd  stloc.s  4
0x502ff  ldloc.s  4
0x50301  ldc.i4.4
0x50302  ble.s    loc_5029E
0x50304  ldloc.2
0x50305  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5030a  ldstr    aModifiedon// "modifiedon"
0x5030f  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x50314  ldloc.2
0x50315  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5031a  ldstr    aProcessid// "processid"
0x5031f  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x50324  ldarg.3
0x50325  brfalse.s loc_50347
0x50327  ldloc.2
0x50328  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5032d  ldstr    aProcessstageid// "processstageid"
0x50332  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x50337  ldloc.2
0x50338  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5033d  ldstr    aTraversedpath// "traversedpath"
0x50342  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x50347  ldstr    aBusinessproces// "BusinessProcessFlowInstance"
0x5034c  ldloc.0
0x5034d  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext <>c__DisplayClass19_0::executionContext
0x50352  call     class Microsoft.Crm.BusinessEntities.BusinessProcessObject Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string entityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x50357  ldloc.2
0x50358  ldloc.0
0x50359  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext <>c__DisplayClass19_0::executionContext
0x5035e  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x50363  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x50368  call     class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollectionExtensions::ToCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityCollection)
0x5036d  ldloc.0
0x5036e  ldftn    instance bool <>c__DisplayClass19_0::<RetrieveDefaultProcessInstanceFallback>b__0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity instance)
0x50374  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, bool>::.ctor(object, native int)
0x50379  call     T0x2B000064
0x5037e  stloc.3
0x5037f  ldloc.3
0x50380  brfalse.s loc_5038A
0x50382  ldloc.3
0x50383  call     T0x2B000065
0x50388  brtrue.s loc_5038C
0x5038a  ldnull
0x5038b  ret
0x5038c  ldloc.3
0x5038d  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.DateTime> <>c::<>9__19_1
0x50392  dup
0x50393  brtrue.s loc_503AC
0x50395  pop
0x50396  ldsfld   class <>c <>c::<>9
0x5039b  ldftn    instance valuetype [mscorlib]System.DateTime <>c::<RetrieveDefaultProcessInstanceFallback>b__19_1(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity instance)
0x503a1  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.DateTime>::.ctor(object, native int)
0x503a6  dup
0x503a7  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.DateTime> <>c::<>9__19_1
0x503ac  call     T0x2B000066
0x503b1  call     T0x2B000067
0x503b6  ret
```
