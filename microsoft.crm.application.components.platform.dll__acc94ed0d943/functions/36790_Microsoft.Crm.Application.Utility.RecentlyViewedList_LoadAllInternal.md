# Microsoft.Crm.Application.Utility.RecentlyViewedList::LoadAllInternal

- ea: `0x36790`
- end: `0x36950`
- name: `Microsoft.Crm.Application.Utility.RecentlyViewedList::LoadAllInternal`
- size: `448`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x36780`
- `0x37060`
- `0x37470`

## callees

- `0x36790`
- `0x59800`
- `0x5be20`

## string_xrefs

- `0x367a1`: `recentlyviewedxml`
- `0x367f3`: `recentlyviewedxml`
- `0x3680a`: `recentlyviewedxml`
- `0x3687b`: `recentlyviewedxml`
- `0x3688e`: `recentlyviewedxml`

## pseudocode

```c

```

## disassembly

```asm
0x36790  ldstr    aUserentityuise// "userentityuisettings"
0x36795  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x3679a  stloc.0
0x3679b  ldloc.0
0x3679c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x367a1  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x367a6  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x367ab  ldloc.0
0x367ac  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x367b1  ldstr    aObjecttypecode// "objecttypecode"
0x367b6  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x367bb  ldloc.0
0x367bc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x367c1  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x367c6  ldstr    aOwnerid// "ownerid"
0x367cb  ldc.i4.0
0x367cc  ldarg.0
0x367cd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserId()
0x367d2  box      [mscorlib]System.Guid
0x367d7  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x367dc  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x367e1  pop
0x367e2  ldarg.1
0x367e3  brfalse.s loc_367ED
0x367e5  ldarg.1
0x367e6  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<int32>::get_Count()
0x367eb  brtrue.s loc_36824
0x367ed  ldloc.0
0x367ee  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x367f3  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x367f8  ldc.i4.s 0xD
0x367fa  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator)
0x367ff  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x36804  ldloc.0
0x36805  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x3680a  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x3680f  ldc.i4.1
0x36810  ldsfld   string [mscorlib]System.String::Empty
0x36815  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x3681a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x3681f  br       loc_368F6
0x36824  ldarg.1
0x36825  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<int32>::get_Count()
0x3682a  newarr   [mscorlib]System.Object
0x3682f  stloc.2
0x36830  ldc.i4.0
0x36831  stloc.3
0x36832  ldarg.1
0x36833  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<int32>::GetEnumerator()
0x36838  stloc.s  8
0x3683a  br.s     loc_36853
0x3683c  ldloc.s  8
0x3683e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<int32>::get_Current()
0x36843  stloc.s  9
0x36845  ldloc.2
0x36846  ldloc.3
0x36847  ldloc.s  9
0x36849  box      [mscorlib]System.Int32
0x3684e  stelem.ref
0x3684f  ldloc.3
0x36850  ldc.i4.1
0x36851  add
0x36852  stloc.3
0x36853  ldloc.s  8
0x36855  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3685a  brtrue.s loc_3683C
0x3685c  leave.s  loc_3686A
0x3685e  ldloc.s  8
0x36860  brfalse.s loc_36869
0x36862  ldloc.s  8
0x36864  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36869  endfinally
0x3686a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x3686f  stloc.s  4
0x36871  ldloc.s  4
0x36873  ldc.i4.0
0x36874  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x36879  ldloc.s  4
0x3687b  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x36880  ldc.i4.s 0xD
0x36882  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator)
0x36887  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x3688c  ldloc.s  4
0x3688e  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x36893  ldc.i4.1
0x36894  ldsfld   string [mscorlib]System.String::Empty
0x36899  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x3689e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x368a3  ldstr    aObjecttypecode// "objecttypecode"
0x368a8  ldc.i4.8
0x368a9  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator)
0x368ae  stloc.s  5
0x368b0  ldloc.s  5
0x368b2  ldloc.2
0x368b3  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::set_Values(object[])
0x368b8  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x368bd  stloc.s  6
0x368bf  ldloc.s  6
0x368c1  ldloc.s  5
0x368c3  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x368c8  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x368cd  stloc.s  7
0x368cf  ldloc.s  7
0x368d1  ldc.i4.1
0x368d2  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x368d7  ldloc.s  7
0x368d9  ldloc.s  4
0x368db  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x368e0  ldloc.s  7
0x368e2  ldloc.s  6
0x368e4  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x368e9  ldloc.0
0x368ea  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x368ef  ldloc.s  7
0x368f1  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x368f6  ldloc.0
0x368f7  ldarg.0
0x368f8  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x368fd  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity>::.ctor()
0x36902  stloc.1
0x36903  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x36908  stloc.s  0xA
0x3690a  br.s     loc_36937
0x3690c  ldloc.s  0xA
0x3690e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x36913  stloc.s  0xB
0x36915  ldloc.s  0xB
0x36917  ldstr    aObjecttypecode// "objecttypecode"
0x3691c  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x36921  unbox.any [mscorlib]System.Int32
0x36926  stloc.s  0xC
0x36928  ldloc.s  0xC
0x3692a  ldc.i4.0
0x3692b  ble.s    loc_36937
0x3692d  ldloc.1
0x3692e  ldloc.s  0xC
0x36930  ldloc.s  0xB
0x36932  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity>::set_Item(var<u1>, !!T0)
0x36937  ldloc.s  0xA
0x36939  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3693e  brtrue.s loc_3690C
0x36940  leave.s  loc_3694E
0x36942  ldloc.s  0xA
0x36944  brfalse.s loc_3694D
0x36946  ldloc.s  0xA
0x36948  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3694d  endfinally
0x3694e  ldloc.1
0x3694f  ret
```
