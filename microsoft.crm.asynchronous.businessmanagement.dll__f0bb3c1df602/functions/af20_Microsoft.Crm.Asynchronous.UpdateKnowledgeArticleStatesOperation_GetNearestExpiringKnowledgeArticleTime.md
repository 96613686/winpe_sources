# Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::GetNearestExpiringKnowledgeArticleTime

- ea: `0xaf20`
- end: `0xb025`
- name: `Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::GetNearestExpiringKnowledgeArticleTime`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0xaec0`

## callees

- `0xaf20`

## string_xrefs

- `0xafab`: `expirationstatusid`

## pseudocode

```c

```

## disassembly

```asm
0xaf20  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0xaf25  stloc.0
0xaf26  ldloc.0
0xaf27  ldstr    aKnowledgeartic// "knowledgearticle"
0xaf2c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0xaf31  ldloc.0
0xaf32  ldc.i4.1
0xaf33  newarr   [mscorlib]System.String
0xaf38  dup
0xaf39  ldc.i4.0
0xaf3a  ldstr    aExpirationdate// "expirationdate"
0xaf3f  stelem.ref
0xaf40  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xaf45  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0xaf4a  ldloc.0
0xaf4b  ldstr    aExpirationdate// "expirationdate"
0xaf50  ldc.i4.0
0xaf51  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0xaf56  ldloc.0
0xaf57  ldc.i4.1
0xaf58  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xaf5d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_TopCount(valuetype [mscorlib]System.Nullable`1<int32>)
0xaf62  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0xaf67  stloc.1
0xaf68  ldloc.1
0xaf69  ldc.i4.0
0xaf6a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0xaf6f  ldloc.1
0xaf70  ldstr    aStatecode// "statecode"
0xaf75  ldc.i4.0
0xaf76  ldc.i4.3
0xaf77  box      [mscorlib]System.Int32
0xaf7c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xaf81  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0xaf86  ldloc.1
0xaf87  ldstr    aExpirationdate// "expirationdate"
0xaf8c  ldc.i4.s 0xD
0xaf8e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xaf93  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0xaf98  ldloc.1
0xaf99  ldstr    aExpirationstat// "expirationstateid"
0xaf9e  ldc.i4.s 0xD
0xafa0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xafa5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0xafaa  ldloc.1
0xafab  ldstr    aExpirationstat_0// "expirationstatusid"
0xafb0  ldc.i4.s 0xD
0xafb2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xafb7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0xafbc  ldloc.0
0xafbd  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xafc2  ldloc.1
0xafc3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0xafc8  ldarg.0
0xafc9  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStatesOperation::_sdkService
0xafce  ldloc.0
0xafcf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0xafd4  stloc.2
0xafd5  ldloc.2
0xafd6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xafdb  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0xafe0  ldc.i4.0
0xafe1  ble.s    loc_B023
0xafe3  ldarg.1
0xafe4  ldloc.2
0xafe5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xafea  ldc.i4.0
0xafeb  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0xaff0  ldstr    aExpirationdate// "expirationdate"
0xaff5  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xaffa  unbox.any [mscorlib]System.DateTime
0xafff  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xb004  brfalse.s loc_B023
0xb006  ldloc.2
0xb007  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xb00c  ldc.i4.0
0xb00d  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0xb012  ldstr    aExpirationdate// "expirationdate"
0xb017  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0xb01c  unbox.any [mscorlib]System.DateTime
0xb021  starg.s  1
0xb023  ldarg.1
0xb024  ret
```
