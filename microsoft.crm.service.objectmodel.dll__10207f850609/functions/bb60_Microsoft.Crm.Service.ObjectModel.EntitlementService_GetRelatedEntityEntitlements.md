# Microsoft.Crm.Service.ObjectModel.EntitlementService::GetRelatedEntityEntitlements

- ea: `0xbb60`
- end: `0xbc9f`
- name: `Microsoft.Crm.Service.ObjectModel.EntitlementService::GetRelatedEntityEntitlements`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xb5f0`

## callees

- `0xbb60`
- `0x1adc0`

## string_xrefs

- `0xbb9f`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0xbb60  newobj   instance void <>c__DisplayClass9_0::.ctor()
0xbb65  stloc.0
0xbb66  ldloc.0
0xbb67  ldarg.2
0xbb68  stfld    string <>c__DisplayClass9_0::filterAttributeName
0xbb6d  ldloc.0
0xbb6e  ldarg.3
0xbb6f  stfld    string <>c__DisplayClass9_0::filterAttributeValue
0xbb74  ldstr    aEntitlement// "Entitlement"
0xbb79  ldarg.s  6
0xbb7b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xbb80  stloc.1
0xbb81  ldloc.1
0xbb82  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xbb87  ldc.i4.4
0xbb88  newarr   [mscorlib]System.String
0xbb8d  dup
0xbb8e  ldc.i4.0
0xbb8f  ldstr    aEntitlementid// "entitlementid"
0xbb94  stelem.ref
0xbb95  dup
0xbb96  ldc.i4.1
0xbb97  ldstr    aName// "name"
0xbb9c  stelem.ref
0xbb9d  dup
0xbb9e  ldc.i4.2
0xbb9f  ldstr    aCreatedon// "createdon"
0xbba4  stelem.ref
0xbba5  dup
0xbba6  ldc.i4.3
0xbba7  ldstr    aStatecode// "statecode"
0xbbac  stelem.ref
0xbbad  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xbbb2  ldloc.1
0xbbb3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xbbb8  ldc.i4.0
0xbbb9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0xbbbe  ldloc.1
0xbbbf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xbbc4  ldstr    aStatecode// "statecode"
0xbbc9  ldc.i4.0
0xbbca  ldstr    aActive// "Active"
0xbbcf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xbbd4  pop
0xbbd5  ldarg.s  5
0xbbd7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xbbdc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Filters()
0xbbe1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression>::get_Count()
0xbbe6  ldc.i4.0
0xbbe7  ble.s    loc_BC2C
0xbbe9  ldarg.s  5
0xbbeb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xbbf0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Filters()
0xbbf5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression>::GetEnumerator()
0xbbfa  stloc.3
0xbbfb  br.s     loc_BC13
0xbbfd  ldloca.s 3
0xbbff  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression>::get_Current()
0xbc04  stloc.s  4
0xbc06  ldloc.1
0xbc07  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xbc0c  ldloc.s  4
0xbc0e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0xbc13  ldloca.s 3
0xbc15  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression>::MoveNext()
0xbc1a  brtrue.s loc_BBFD
0xbc1c  leave.s  loc_BC2C
0xbc1e  ldloca.s 3
0xbc20  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression>
0xbc26  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbc2b  endfinally
0xbc2c  ldloc.1
0xbc2d  ldarg.s  4
0xbc2f  ldstr    aEntitlementid// "entitlementid"
0xbc34  ldstr    aEntitlementid// "entitlementid"
0xbc39  ldc.i4.0
0xbc3a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xbc3f  dup
0xbc40  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0xbc45  ldloc.0
0xbc46  ldfld    string <>c__DisplayClass9_0::filterAttributeName
0xbc4b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xbc50  ldstr    aEntityentitlem// "EntityEntitlements"
0xbc55  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::set_TableAlias(string)
0xbc5a  ldloc.0
0xbc5b  ldarg.0
0xbc5c  ldloc.1
0xbc5d  ldarg.s  6
0xbc5f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xbc64  call     T0x2B000001
0xbc69  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> <>c__DisplayClass9_0::allEntityEntitlements
0xbc6e  ldloc.0
0xbc6f  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> <>c__DisplayClass9_0::allEntityEntitlements
0xbc74  ldloc.0
0xbc75  ldftn    instance bool <>c__DisplayClass9_0::<GetRelatedEntityEntitlements>b__0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity x)
0xbc7b  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, bool>::.ctor(object, native int)
0xbc80  call     T0x2B000006
0xbc85  ldarg.1
0xbc86  ldloc.0
0xbc87  ldftn    instance bool <>c__DisplayClass9_0::<GetRelatedEntityEntitlements>b__1(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity e)
0xbc8d  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, bool>::.ctor(object, native int)
0xbc92  call     T0x2B000006
0xbc97  stloc.2
0xbc98  ldloc.2
0xbc99  call     T0x2B000007
0xbc9e  ret
```
