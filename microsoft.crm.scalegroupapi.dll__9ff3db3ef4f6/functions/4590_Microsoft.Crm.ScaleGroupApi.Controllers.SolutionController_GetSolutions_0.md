# Microsoft.Crm.ScaleGroupApi.Controllers.SolutionController::GetSolutions_0

- ea: `0x4590`
- end: `0x4636`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.SolutionController::GetSolutions_0`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3af0`

## callees

- `0xe80`
- `0xeb0`
- `0x4590`

## pseudocode

```c

```

## disassembly

```asm
0x4590  ldarg.0
0x4591  call     class Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::CreateInstance(valuetype [mscorlib]System.Guid orgId)
0x4596  stloc.0
0x4597  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x459c  stloc.1
0x459d  ldloc.1
0x459e  ldstr    aUniquename// "uniquename"
0x45a3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x45a8  ldloc.1
0x45a9  ldc.i4.0
0x45aa  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x45af  ldloc.1
0x45b0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x45b5  ldarg.1
0x45b6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x45bb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x45c0  stloc.2
0x45c1  ldloc.2
0x45c2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x45c7  ldloc.1
0x45c8  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x45cd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression::.ctor()
0x45d2  stloc.3
0x45d3  ldloc.3
0x45d4  ldstr    aVersion// "version"
0x45d9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression::set_AttributeName(string)
0x45de  ldloc.3
0x45df  ldc.i4.1
0x45e0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression::set_OrderType(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x45e5  ldstr    aSolution_0// "solution"
0x45ea  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x45ef  stloc.s  4
0x45f1  ldloc.s  4
0x45f3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x45f8  ldc.i4.1
0x45f9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::set_AllColumns(bool)
0x45fe  ldloc.s  4
0x4600  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x4605  ldloc.2
0x4606  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x460b  ldloc.s  4
0x460d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Orders()
0x4612  ldloc.3
0x4613  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderExpression>::Add(var<u1>)
0x4618  ldloc.0
0x4619  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::get_Sdk()
0x461e  ldloc.s  4
0x4620  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x4625  stloc.s  5
0x4627  leave.s  loc_4633
0x4629  ldloc.0
0x462a  brfalse.s loc_4632
0x462c  ldloc.0
0x462d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4632  endfinally
0x4633  ldloc.s  5
0x4635  ret
```
