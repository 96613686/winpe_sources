# Microsoft.Crm.Service.ObjectModel.EntitlementService::IsRelatedEntityEntitlementValid

- ea: `0xba50`
- end: `0xbb5c`
- name: `Microsoft.Crm.Service.ObjectModel.EntitlementService::IsRelatedEntityEntitlementValid`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xb8e0`

## callees

- `0xba50`
- `0x1ad60`

## string_xrefs

- `0xba90`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0xba50  newobj   instance void <>c__DisplayClass8_0::.ctor()
0xba55  stloc.0
0xba56  ldloc.0
0xba57  ldarg.3
0xba58  stfld    string <>c__DisplayClass8_0::filterAttributeName
0xba5d  ldloc.0
0xba5e  ldarg.s  4
0xba60  stfld    string <>c__DisplayClass8_0::filterAttributeValue
0xba65  ldstr    aEntitlement// "Entitlement"
0xba6a  ldarg.s  6
0xba6c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xba71  stloc.1
0xba72  ldloc.1
0xba73  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xba78  ldc.i4.4
0xba79  newarr   [mscorlib]System.String
0xba7e  dup
0xba7f  ldc.i4.0
0xba80  ldstr    aEntitlementid// "entitlementid"
0xba85  stelem.ref
0xba86  dup
0xba87  ldc.i4.1
0xba88  ldstr    aName// "name"
0xba8d  stelem.ref
0xba8e  dup
0xba8f  ldc.i4.2
0xba90  ldstr    aCreatedon// "createdon"
0xba95  stelem.ref
0xba96  dup
0xba97  ldc.i4.3
0xba98  ldstr    aStatecode// "statecode"
0xba9d  stelem.ref
0xba9e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xbaa3  ldloc.1
0xbaa4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xbaa9  ldc.i4.0
0xbaaa  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0xbaaf  ldloc.1
0xbab0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xbab5  ldstr    aEntitlementid// "entitlementid"
0xbaba  ldc.i4.0
0xbabb  ldarg.1
0xbabc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xbac1  pop
0xbac2  ldloc.1
0xbac3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xbac8  ldstr    aCustomerid// "customerid"
0xbacd  ldc.i4.0
0xbace  ldarg.2
0xbacf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xbad4  pop
0xbad5  ldloc.1
0xbad6  ldarg.s  5
0xbad8  ldstr    aEntitlementid// "entitlementid"
0xbadd  ldstr    aEntitlementid// "entitlementid"
0xbae2  ldc.i4.0
0xbae3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xbae8  dup
0xbae9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xbaee  ldloc.0
0xbaef  ldfld    string <>c__DisplayClass8_0::filterAttributeName
0xbaf4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xbaf9  dup
0xbafa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xbaff  ldstr    aEntitlementid// "entitlementid"
0xbb04  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xbb09  ldstr    aEntityentitlem// "EntityEntitlements"
0xbb0e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::set_TableAlias(string)
0xbb13  ldarg.0
0xbb14  ldloc.1
0xbb15  ldarg.s  6
0xbb17  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xbb1c  call     T0x2B000001
0xbb21  stloc.2
0xbb22  ldloc.2
0xbb23  brfalse.s loc_BB58
0xbb25  ldloc.2
0xbb26  call     T0x2B000005
0xbb2b  ldc.i4.1
0xbb2c  blt.s    loc_BB58
0xbb2e  ldloc.2
0xbb2f  ldloc.0
0xbb30  ldftn    instance bool <>c__DisplayClass8_0::<IsRelatedEntityEntitlementValid>b__0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity x)
0xbb36  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, bool>::.ctor(object, native int)
0xbb3b  call     T0x2B000006
0xbb40  stloc.s  4
0xbb42  ldloc.s  4
0xbb44  brfalse.s loc_BB54
0xbb46  ldloc.s  4
0xbb48  call     T0x2B000005
0xbb4d  ldc.i4.1
0xbb4e  blt.s    loc_BB54
0xbb50  ldc.i4.1
0xbb51  stloc.3
0xbb52  br.s     loc_BB5A
0xbb54  ldc.i4.0
0xbb55  stloc.3
0xbb56  br.s     loc_BB5A
0xbb58  ldc.i4.1
0xbb59  stloc.3
0xbb5a  ldloc.3
0xbb5b  ret
```
