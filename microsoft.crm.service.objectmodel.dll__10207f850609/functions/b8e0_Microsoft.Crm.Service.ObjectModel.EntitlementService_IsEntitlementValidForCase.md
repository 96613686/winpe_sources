# Microsoft.Crm.Service.ObjectModel.EntitlementService::IsEntitlementValidForCase

- ea: `0xb8e0`
- end: `0xb9f5`
- name: `Microsoft.Crm.Service.ObjectModel.EntitlementService::IsEntitlementValidForCase`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1210`

## callees

- `0xb8e0`
- `0xba50`

## string_xrefs

- `0xb91f`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0xb8e0  ldarg.2
0xb8e1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb8e6  brtrue   loc_B9F3
0xb8eb  ldarg.s  5
0xb8ed  brfalse  loc_B9F3
0xb8f2  ldc.i4.1
0xb8f3  stloc.0
0xb8f4  ldstr    aEntitlement// "Entitlement"
0xb8f9  ldarg.s  6
0xb8fb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xb900  stloc.1
0xb901  ldloc.1
0xb902  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xb907  ldc.i4.4
0xb908  newarr   [mscorlib]System.String
0xb90d  dup
0xb90e  ldc.i4.0
0xb90f  ldstr    aEntitlementid// "entitlementid"
0xb914  stelem.ref
0xb915  dup
0xb916  ldc.i4.1
0xb917  ldstr    aName// "name"
0xb91c  stelem.ref
0xb91d  dup
0xb91e  ldc.i4.2
0xb91f  ldstr    aCreatedon// "createdon"
0xb924  stelem.ref
0xb925  dup
0xb926  ldc.i4.3
0xb927  ldstr    aStatecode// "statecode"
0xb92c  stelem.ref
0xb92d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xb932  ldloc.1
0xb933  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xb938  ldc.i4.0
0xb939  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0xb93e  ldloc.1
0xb93f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xb944  ldstr    aEntitlementid// "entitlementid"
0xb949  ldc.i4.0
0xb94a  ldarg.1
0xb94b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xb950  pop
0xb951  ldloc.1
0xb952  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xb957  ldstr    aStatecode// "statecode"
0xb95c  ldc.i4.0
0xb95d  ldc.i4.1
0xb95e  box      [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.EntitlementState
0xb963  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xb968  pop
0xb969  ldloc.1
0xb96a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xb96f  ldstr    aCustomerid// "customerid"
0xb974  ldc.i4.0
0xb975  ldarg.2
0xb976  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xb97b  pop
0xb97c  ldarg.0
0xb97d  ldloc.1
0xb97e  ldarg.s  6
0xb980  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xb985  stloc.2
0xb986  ldloc.2
0xb987  brfalse.s loc_B9EF
0xb989  ldloc.2
0xb98a  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xb98f  ldc.i4.1
0xb990  blt.s    loc_B9EF
0xb992  ldc.i4.1
0xb993  stloc.0
0xb994  ldloc.0
0xb995  brfalse.s loc_B9F3
0xb997  ldarg.3
0xb998  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb99d  brfalse.s loc_B9A8
0xb99f  ldarg.s  4
0xb9a1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb9a6  brtrue.s loc_B9F3
0xb9a8  ldarg.3
0xb9a9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb9ae  brtrue.s loc_B9C9
0xb9b0  ldarg.0
0xb9b1  ldarg.1
0xb9b2  ldarg.2
0xb9b3  ldstr    aContactid// "contactid"
0xb9b8  ldarg.3
0xb9b9  ldstr    aEntitlementcon// "EntitlementContacts"
0xb9be  ldarg.s  6
0xb9c0  call     instance bool Microsoft.Crm.Service.ObjectModel.EntitlementService::IsRelatedEntityEntitlementValid(string entitlementValue, string customerValue, string filterAttributeName, string filterAttributeValue, string intersectionEntityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xb9c5  brtrue.s loc_B9C9
0xb9c7  ldc.i4.0
0xb9c8  ret
0xb9c9  ldloc.0
0xb9ca  brfalse.s loc_B9F3
0xb9cc  ldarg.s  4
0xb9ce  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb9d3  brtrue.s loc_B9F3
0xb9d5  ldarg.0
0xb9d6  ldarg.1
0xb9d7  ldarg.2
0xb9d8  ldstr    aProductid// "productid"
0xb9dd  ldarg.s  4
0xb9df  ldstr    aEntitlementpro// "EntitlementProducts"
0xb9e4  ldarg.s  6
0xb9e6  call     instance bool Microsoft.Crm.Service.ObjectModel.EntitlementService::IsRelatedEntityEntitlementValid(string entitlementValue, string customerValue, string filterAttributeName, string filterAttributeValue, string intersectionEntityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xb9eb  brtrue.s loc_B9F3
0xb9ed  ldc.i4.0
0xb9ee  ret
0xb9ef  ldc.i4.0
0xb9f0  dup
0xb9f1  stloc.0
0xb9f2  ret
0xb9f3  ldc.i4.1
0xb9f4  ret
```
