# Microsoft.Crm.Caching.UserEntityUISettingsWebServiceCacheLoader::LoadCacheData_0

- ea: `0x158f0`
- end: `0x159dd`
- name: `Microsoft.Crm.Caching.UserEntityUISettingsWebServiceCacheLoader::LoadCacheData_0`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x158e0`

## callees

- `0x127e0`
- `0x158f0`
- `0x59800`

## string_xrefs

- `0x1591f`: `userentityuisettingsid`
- `0x15937`: `taborderxml`
- `0x1593f`: `readingpanexml`
- `0x15947`: `lastviewedformxml`
- `0x15957`: `recentlyviewedxml`

## pseudocode

```c

```

## disassembly

```asm
0x158f0  ldc.i4.0
0x158f1  stloc.0
0x158f2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x158f7  stloc.1
0x158f8  ldarg.1
0x158f9  ldloca.s 0
0x158fb  ldloca.s 1
0x158fd  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::ExtractFromKey(string, int32&, valuetype [mscorlib]System.Guid&)
0x15902  ldstr    aUserentityuise// "userentityuisettings"
0x15907  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x1590c  stloc.2
0x1590d  ldloc.2
0x1590e  ldc.i4.s 9
0x15910  newarr   [mscorlib]System.String
0x15915  dup
0x15916  ldc.i4.0
0x15917  ldstr    aOwnerid// "ownerid"
0x1591c  stelem.ref
0x1591d  dup
0x1591e  ldc.i4.1
0x1591f  ldstr    aUserentityuise_0// "userentityuisettingsid"
0x15924  stelem.ref
0x15925  dup
0x15926  ldc.i4.2
0x15927  ldstr    aOwningbusiness// "owningbusinessunit"
0x1592c  stelem.ref
0x1592d  dup
0x1592e  ldc.i4.3
0x1592f  ldstr    aObjecttypecode// "objecttypecode"
0x15934  stelem.ref
0x15935  dup
0x15936  ldc.i4.4
0x15937  ldstr    aTaborderxml// "taborderxml"
0x1593c  stelem.ref
0x1593d  dup
0x1593e  ldc.i4.5
0x1593f  ldstr    aReadingpanexml// "readingpanexml"
0x15944  stelem.ref
0x15945  dup
0x15946  ldc.i4.6
0x15947  ldstr    aLastviewedform// "lastviewedformxml"
0x1594c  stelem.ref
0x1594d  dup
0x1594e  ldc.i4.7
0x1594f  ldstr    aShowinaddressb// "showinaddressbook"
0x15954  stelem.ref
0x15955  dup
0x15956  ldc.i4.8
0x15957  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x1595c  stelem.ref
0x1595d  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0x15962  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x15967  ldloc.2
0x15968  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x1596d  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x15972  ldstr    aOwnerid// "ownerid"
0x15977  ldc.i4.0
0x15978  ldloc.1
0x15979  box      [mscorlib]System.Guid
0x1597e  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x15983  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x15988  pop
0x15989  ldloc.2
0x1598a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x1598f  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x15994  ldstr    aObjecttypecode// "objecttypecode"
0x15999  ldc.i4.0
0x1599a  ldloc.0
0x1599b  box      [mscorlib]System.Int32
0x159a0  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x159a5  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x159aa  pop
0x159ab  ldloc.2
0x159ac  ldarg.2
0x159ad  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x159b2  stloc.3
0x159b3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsData::.ctor()
0x159b8  stloc.s  4
0x159ba  ldloc.3
0x159bb  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x159c0  ldc.i4.0
0x159c1  ble.s    loc_159DA
0x159c3  ldloc.3
0x159c4  ldc.i4.0
0x159c5  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x159ca  newobj   instance void Microsoft.Crm.Caching.CacheApplicationEntityWrapper::.ctor(class Microsoft.Crm.Application.Platform.Entity entity)
0x159cf  stloc.s  5
0x159d1  ldloc.s  4
0x159d3  ldloc.s  5
0x159d5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsData::Initialize(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ICacheEntityWrapper)
0x159da  ldloc.s  4
0x159dc  ret
```
