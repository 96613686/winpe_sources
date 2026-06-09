# Microsoft.Crm.Application.Utility.LookupMruList::loadAllInternal

- ea: `0x35460`
- end: `0x35611`
- name: `Microsoft.Crm.Application.Utility.LookupMruList::loadAllInternal`
- size: `433`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x35450`
- `0x35ae0`

## callees

- `0x16b80`
- `0x16b90`
- `0x35460`
- `0x59800`
- `0x5be20`

## string_xrefs

- `0x35471`: `lookupmruxml`
- `0x354cd`: `lookupmruxml`
- `0x354e4`: `lookupmruxml`
- `0x3553e`: `lookupmruxml`
- `0x35550`: `lookupmruxml`

## pseudocode

```c

```

## disassembly

```asm
0x35460  ldstr    aUserentityuise// "userentityuisettings"
0x35465  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x3546a  stloc.0
0x3546b  ldloc.0
0x3546c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x35471  ldstr    aLookupmruxml// "lookupmruxml"
0x35476  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x3547b  ldloc.0
0x3547c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x35481  ldstr    aObjecttypecode// "objecttypecode"
0x35486  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x3548b  ldloc.0
0x3548c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x35491  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x35496  ldstr    aOwnerid// "ownerid"
0x3549b  ldc.i4.0
0x3549c  call     class Microsoft.Crm.Application.ClientOrganizationContext Microsoft.Crm.Application.ClientOrganizationContext::get_Instance()
0x354a1  ldarg.1
0x354a2  callvirt instance class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx Microsoft.Crm.Application.ClientOrganizationContext::Get(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x354a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_UserId()
0x354ac  box      [mscorlib]System.Guid
0x354b1  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x354b6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x354bb  pop
0x354bc  ldarg.0
0x354bd  brfalse.s loc_354C7
0x354bf  ldarg.0
0x354c0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x354c5  brtrue.s loc_354FE
0x354c7  ldloc.0
0x354c8  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x354cd  ldstr    aLookupmruxml// "lookupmruxml"
0x354d2  ldc.i4.s 0xD
0x354d4  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator)
0x354d9  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x354de  ldloc.0
0x354df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x354e4  ldstr    aLookupmruxml// "lookupmruxml"
0x354e9  ldc.i4.1
0x354ea  ldsfld   string [mscorlib]System.String::Empty
0x354ef  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x354f4  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x354f9  br       loc_355B7
0x354fe  ldarg.0
0x354ff  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x35504  newarr   [mscorlib]System.Object
0x35509  stloc.2
0x3550a  ldc.i4.0
0x3550b  stloc.s  7
0x3550d  br.s     loc_35526
0x3550f  ldloc.2
0x35510  ldloc.s  7
0x35512  ldarg.0
0x35513  ldloc.s  7
0x35515  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<int32>::get_Item(!!T0)
0x3551a  box      [mscorlib]System.Int32
0x3551f  stelem.ref
0x35520  ldloc.s  7
0x35522  ldc.i4.1
0x35523  add
0x35524  stloc.s  7
0x35526  ldloc.s  7
0x35528  ldarg.0
0x35529  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x3552e  blt.s    loc_3550F
0x35530  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x35535  stloc.3
0x35536  ldloc.3
0x35537  ldc.i4.0
0x35538  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x3553d  ldloc.3
0x3553e  ldstr    aLookupmruxml// "lookupmruxml"
0x35543  ldc.i4.s 0xD
0x35545  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator)
0x3554a  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x3554f  ldloc.3
0x35550  ldstr    aLookupmruxml// "lookupmruxml"
0x35555  ldc.i4.1
0x35556  ldsfld   string [mscorlib]System.String::Empty
0x3555b  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x35560  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x35565  ldstr    aObjecttypecode// "objecttypecode"
0x3556a  ldc.i4.8
0x3556b  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator)
0x35570  stloc.s  4
0x35572  ldloc.s  4
0x35574  ldloc.2
0x35575  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::set_Values(object[])
0x3557a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x3557f  stloc.s  5
0x35581  ldloc.s  5
0x35583  ldloc.s  4
0x35585  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x3558a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x3558f  stloc.s  6
0x35591  ldloc.s  6
0x35593  ldc.i4.1
0x35594  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x35599  ldloc.s  6
0x3559b  ldloc.3
0x3559c  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x355a1  ldloc.s  6
0x355a3  ldloc.s  5
0x355a5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x355aa  ldloc.0
0x355ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x355b0  ldloc.s  6
0x355b2  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x355b7  ldloc.0
0x355b8  ldarg.1
0x355b9  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x355be  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity>::.ctor()
0x355c3  stloc.1
0x355c4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x355c9  stloc.s  8
0x355cb  br.s     loc_355F8
0x355cd  ldloc.s  8
0x355cf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x355d4  stloc.s  9
0x355d6  ldloc.s  9
0x355d8  ldstr    aObjecttypecode// "objecttypecode"
0x355dd  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x355e2  unbox.any [mscorlib]System.Int32
0x355e7  stloc.s  0xA
0x355e9  ldloc.s  0xA
0x355eb  ldc.i4.0
0x355ec  ble.s    loc_355F8
0x355ee  ldloc.1
0x355ef  ldloc.s  0xA
0x355f1  ldloc.s  9
0x355f3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity>::set_Item(var<u1>, !!T0)
0x355f8  ldloc.s  8
0x355fa  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x355ff  brtrue.s loc_355CD
0x35601  leave.s  loc_3560F
0x35603  ldloc.s  8
0x35605  brfalse.s loc_3560E
0x35607  ldloc.s  8
0x35609  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3560e  endfinally
0x3560f  ldloc.1
0x35610  ret
```
