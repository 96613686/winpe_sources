# Microsoft.Crm.ScaleGroupApi.Controllers.SolutionController::GetSingleBaseSolution

- ea: `0x44d0`
- end: `0x4581`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.SolutionController::GetSingleBaseSolution`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3760`

## callees

- `0xe80`
- `0xeb0`
- `0x44d0`

## pseudocode

```c

```

## disassembly

```asm
0x44d0  ldarg.0
0x44d1  call     class Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::CreateInstance(valuetype [mscorlib]System.Guid orgId)
0x44d6  stloc.0
0x44d7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x44dc  stloc.1
0x44dd  ldloc.1
0x44de  ldstr    aUniquename// "uniquename"
0x44e3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x44e8  ldloc.1
0x44e9  ldc.i4.0
0x44ea  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x44ef  ldloc.1
0x44f0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x44f5  ldarg.1
0x44f6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x44fb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0x4500  stloc.2
0x4501  ldloc.2
0x4502  ldstr    aVersion// "version"
0x4507  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0x450c  ldloc.2
0x450d  ldc.i4.0
0x450e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x4513  ldloc.2
0x4514  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0x4519  ldarg.2
0x451a  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0x451f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x4524  stloc.3
0x4525  ldloc.3
0x4526  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x452b  ldloc.1
0x452c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x4531  ldloc.3
0x4532  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x4537  ldloc.2
0x4538  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x453d  ldstr    aSolution_0// "solution"
0x4542  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x4547  stloc.s  4
0x4549  ldloc.s  4
0x454b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x4550  ldc.i4.1
0x4551  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::set_AllColumns(bool)
0x4556  ldloc.s  4
0x4558  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x455d  ldloc.3
0x455e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x4563  ldloc.0
0x4564  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::get_Sdk()
0x4569  ldloc.s  4
0x456b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x4570  stloc.s  5
0x4572  leave.s  loc_457E
0x4574  ldloc.0
0x4575  brfalse.s loc_457D
0x4577  ldloc.0
0x4578  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x457d  endfinally
0x457e  ldloc.s  5
0x4580  ret
```
