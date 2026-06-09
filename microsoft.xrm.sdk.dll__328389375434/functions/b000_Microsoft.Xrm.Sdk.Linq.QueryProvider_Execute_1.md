# Microsoft.Xrm.Sdk.Linq.QueryProvider::Execute_1

- ea: `0xb000`
- end: `0xb2b1`
- name: `Microsoft.Xrm.Sdk.Linq.QueryProvider::Execute_1`
- size: `689`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callers

- `0xafd0`

## callees

- `0x2e30`
- `0x2e60`
- `0x2e90`
- `0x2eb0`
- `0x30c0`
- `0x8cd0`
- `0x9580`
- `0x9590`
- `0x95a0`
- `0x95b0`
- `0x95f0`
- `0x9a00`
- `0xb000`
- `0xb2c0`
- `0xb3f0`
- `0xb540`
- `0xb650`
- `0xb660`
- `0xdf70`
- `0x125d0`
- `0x125f0`
- `0x12870`
- `0x128c0`
- `0x12910`
- `0x12980`
- `0x224c0`
- `0x224e0`

## string_xrefs

- `0xb1a2`: `Paging cookie required to retrieve more records. Update your query to retrieve with total records below {0}`

## pseudocode

```c

```

## disassembly

```asm
0xb000  ldnull
0xb001  stloc.0
0xb002  ldarg.s  7
0xb004  ldnull
0xb005  stind.ref
0xb006  ldarg.s  8
0xb008  ldc.i4.0
0xb009  stind.i1
0xb00a  ldnull
0xb00b  stloc.1
0xb00c  ldarg.s  5
0xb00e  brfalse.s loc_B04D
0xb010  newobj   instance void Microsoft.Xrm.Sdk.RelationshipQueryCollection::.ctor()
0xb015  dup
0xb016  ldarg.s  5
0xb018  callvirt instance class Microsoft.Xrm.Sdk.Relationship NavigationSource::get_Relationship()
0xb01d  ldarg.1
0xb01e  callvirt instance void class Microsoft.Xrm.Sdk.DataCollection`2<class Microsoft.Xrm.Sdk.Relationship, class Microsoft.Xrm.Sdk.Query.QueryBase>::Add(var<u1>, !!T0)
0xb023  stloc.s  5
0xb025  newobj   instance void Microsoft.Xrm.Sdk.Messages.RetrieveRequest::.ctor()
0xb02a  dup
0xb02b  ldarg.s  5
0xb02d  callvirt instance class Microsoft.Xrm.Sdk.EntityReference NavigationSource::get_Target()
0xb032  callvirt instance void Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_Target(class Microsoft.Xrm.Sdk.EntityReference value)
0xb037  dup
0xb038  newobj   instance void Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0xb03d  callvirt instance void Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_ColumnSet(class Microsoft.Xrm.Sdk.Query.ColumnSet value)
0xb042  dup
0xb043  ldloc.s  5
0xb045  callvirt instance void Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_RelatedEntitiesQuery(class Microsoft.Xrm.Sdk.RelationshipQueryCollection value)
0xb04a  stloc.1
0xb04b  br.s     loc_B05A
0xb04d  newobj   instance void Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0xb052  dup
0xb053  ldarg.1
0xb054  callvirt instance void Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class Microsoft.Xrm.Sdk.Query.QueryBase value)
0xb059  stloc.1
0xb05a  ldloca.s 2
0xb05c  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xb062  ldarg.1
0xb063  callvirt instance class Microsoft.Xrm.Sdk.Query.PagingInfo Microsoft.Xrm.Sdk.Query.QueryExpression::get_PageInfo()
0xb068  brfalse.s loc_B07C
0xb06a  ldloca.s 2
0xb06c  ldarg.1
0xb06d  callvirt instance class Microsoft.Xrm.Sdk.Query.PagingInfo Microsoft.Xrm.Sdk.Query.QueryExpression::get_PageInfo()
0xb072  callvirt instance int32 Microsoft.Xrm.Sdk.Query.PagingInfo::get_Count()
0xb077  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xb07c  ldc.i4.1
0xb07d  stloc.3
0xb07e  ldarg.0
0xb07f  ldloc.1
0xb080  ldarg.1
0xb081  ldarg.s  5
0xb083  ldloca.s 3
0xb085  call     instance bool Microsoft.Xrm.Sdk.Linq.QueryProvider::AdjustPagingInfo(class Microsoft.Xrm.Sdk.OrganizationRequest request, class Microsoft.Xrm.Sdk.Query.QueryExpression qe, class NavigationSource source, [out] bool& moreRecordAfterAdjust)
0xb08a  ldnull
0xb08b  stloc.s  4
0xb08d  brfalse.s loc_B0A6
0xb08f  ldloc.3
0xb090  brtrue.s loc_B099
0xb092  newobj   instance void Microsoft.Xrm.Sdk.EntityCollection::.ctor()
0xb097  br.s     loc_B0A2
0xb099  ldarg.0
0xb09a  ldloc.1
0xb09b  ldarg.s  5
0xb09d  call     instance class Microsoft.Xrm.Sdk.EntityCollection Microsoft.Xrm.Sdk.Linq.QueryProvider::RetrieveEntityCollection(class Microsoft.Xrm.Sdk.OrganizationRequest request, class NavigationSource source)
0xb0a2  stloc.s  4
0xb0a4  br.s     loc_B0B2
0xb0a6  ldarg.0
0xb0a7  ldloc.1
0xb0a8  ldarg.1
0xb0a9  ldarg.s  5
0xb0ab  call     instance class Microsoft.Xrm.Sdk.EntityCollection Microsoft.Xrm.Sdk.Linq.QueryProvider::AdjustEntityCollection(class Microsoft.Xrm.Sdk.OrganizationRequest request, class Microsoft.Xrm.Sdk.Query.QueryExpression qe, class NavigationSource source)
0xb0b0  stloc.s  4
0xb0b2  ldarg.2
0xb0b3  brfalse.s loc_B0D7
0xb0b5  ldloc.s  4
0xb0b7  brfalse.s loc_B0C7
0xb0b9  ldloc.s  4
0xb0bb  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xb0c0  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Entity>::get_Count()
0xb0c5  brtrue.s loc_B0D7
0xb0c7  ldarg.0
0xb0c8  ldstr    aSequenceContai// "Sequence contains no elements"
0xb0cd  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb0d2  callvirt instance void Microsoft.Xrm.Sdk.Linq.QueryProvider::ThrowException(class [mscorlib]System.Exception exception)
0xb0d7  ldarg.3
0xb0d8  brfalse.s loc_B0FD
0xb0da  ldloc.s  4
0xb0dc  brfalse.s loc_B0FD
0xb0de  ldloc.s  4
0xb0e0  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xb0e5  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Entity>::get_Count()
0xb0ea  ldc.i4.1
0xb0eb  ble.s    loc_B0FD
0xb0ed  ldarg.0
0xb0ee  ldstr    aSequenceContai_0// "Sequence contains more than one element"
0xb0f3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb0f8  callvirt instance void Microsoft.Xrm.Sdk.Linq.QueryProvider::ThrowException(class [mscorlib]System.Exception exception)
0xb0fd  ldloc.s  4
0xb0ff  brfalse  loc_B28A
0xb104  ldarg.s  7
0xb106  ldloc.s  4
0xb108  callvirt instance string Microsoft.Xrm.Sdk.EntityCollection::get_PagingCookie()
0xb10d  stind.ref
0xb10e  ldarg.s  8
0xb110  ldloc.s  4
0xb112  callvirt instance bool Microsoft.Xrm.Sdk.EntityCollection::get_MoreRecords()
0xb117  stind.i1
0xb118  ldloc.s  4
0xb11a  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xb11f  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Entity>::get_Count()
0xb124  stloc.s  6
0xb126  ldloc.s  4
0xb128  stloc.s  7
0xb12a  br       loc_B27A
0xb12f  ldloca.s 2
0xb131  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xb136  brfalse.s loc_B16B
0xb138  ldloc.2
0xb139  stloc.s  8
0xb13b  ldloc.s  6
0xb13d  stloc.s  9
0xb13f  ldloca.s 8
0xb141  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xb146  ldloc.s  9
0xb148  cgt
0xb14a  ldloca.s 8
0xb14c  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xb151  and
0xb152  brfalse.s loc_B16B
0xb154  ldarg.1
0xb155  callvirt instance class Microsoft.Xrm.Sdk.Query.PagingInfo Microsoft.Xrm.Sdk.Query.QueryExpression::get_PageInfo()
0xb15a  ldloca.s 2
0xb15c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xb161  ldloc.s  6
0xb163  sub
0xb164  callvirt instance void Microsoft.Xrm.Sdk.Query.PagingInfo::set_Count(int32 value)
0xb169  br.s     loc_B192
0xb16b  ldloca.s 2
0xb16d  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xb172  brfalse.s loc_B192
0xb174  ldloc.2
0xb175  stloc.s  8
0xb177  ldc.i4.0
0xb178  stloc.s  9
0xb17a  ldloca.s 8
0xb17c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xb181  ldloc.s  9
0xb183  cgt
0xb185  ldloca.s 8
0xb187  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xb18c  and
0xb18d  brtrue   loc_B282
0xb192  ldarg.s  7
0xb194  ldind.ref
0xb195  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb19a  brfalse.s loc_B1CA
0xb19c  ldarg.0
0xb19d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb1a2  ldstr    aPagingCookieRe// "Paging cookie required to retrieve more"...
0xb1a7  ldc.i4.1
0xb1a8  newarr   [mscorlib]System.Object
0xb1ad  dup
0xb1ae  ldc.i4.0
0xb1af  ldarg.0
0xb1b0  callvirt instance int32 Microsoft.Xrm.Sdk.Linq.QueryProvider::get_RetrievalUpperLimitWithoutPagingCookie()
0xb1b5  box      [mscorlib]System.Int32
0xb1ba  stelem.ref
0xb1bb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb1c0  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xb1c5  callvirt instance void Microsoft.Xrm.Sdk.Linq.QueryProvider::ThrowException(class [mscorlib]System.Exception exception)
0xb1ca  ldarg.1
0xb1cb  callvirt instance class Microsoft.Xrm.Sdk.Query.PagingInfo Microsoft.Xrm.Sdk.Query.QueryExpression::get_PageInfo()
0xb1d0  ldloc.s  7
0xb1d2  callvirt instance string Microsoft.Xrm.Sdk.EntityCollection::get_PagingCookie()
0xb1d7  callvirt instance void Microsoft.Xrm.Sdk.Query.PagingInfo::set_PagingCookie(string value)
0xb1dc  ldarg.1
0xb1dd  callvirt instance class Microsoft.Xrm.Sdk.Query.PagingInfo Microsoft.Xrm.Sdk.Query.QueryExpression::get_PageInfo()
0xb1e2  dup
0xb1e3  callvirt instance int32 Microsoft.Xrm.Sdk.Query.PagingInfo::get_PageNumber()
0xb1e8  stloc.s  9
0xb1ea  ldloc.s  9
0xb1ec  ldc.i4.1
0xb1ed  add
0xb1ee  callvirt instance void Microsoft.Xrm.Sdk.Query.PagingInfo::set_PageNumber(int32 value)
0xb1f3  ldarg.1
0xb1f4  callvirt instance class Microsoft.Xrm.Sdk.Query.PagingInfo Microsoft.Xrm.Sdk.Query.QueryExpression::get_PageInfo()
0xb1f9  ldarg.1
0xb1fa  callvirt instance class Microsoft.Xrm.Sdk.Query.PagingInfo Microsoft.Xrm.Sdk.Query.QueryExpression::get_PageInfo()
0xb1ff  callvirt instance int32 Microsoft.Xrm.Sdk.Query.PagingInfo::get_Count()
0xb204  ldarg.0
0xb205  callvirt instance int32 Microsoft.Xrm.Sdk.Linq.QueryProvider::get_RetrievalUpperLimitWithoutPagingCookie()
0xb20a  blt.s    loc_B214
0xb20c  ldarg.0
0xb20d  callvirt instance int32 Microsoft.Xrm.Sdk.Linq.QueryProvider::get_RetrievalUpperLimitWithoutPagingCookie()
0xb212  br.s     loc_B21F
0xb214  ldarg.1
0xb215  callvirt instance class Microsoft.Xrm.Sdk.Query.PagingInfo Microsoft.Xrm.Sdk.Query.QueryExpression::get_PageInfo()
0xb21a  callvirt instance int32 Microsoft.Xrm.Sdk.Query.PagingInfo::get_Count()
0xb21f  callvirt instance void Microsoft.Xrm.Sdk.Query.PagingInfo::set_Count(int32 value)
0xb224  ldarg.0
0xb225  ldloc.1
0xb226  ldarg.s  5
0xb228  call     instance class Microsoft.Xrm.Sdk.EntityCollection Microsoft.Xrm.Sdk.Linq.QueryProvider::RetrieveEntityCollection(class Microsoft.Xrm.Sdk.OrganizationRequest request, class NavigationSource source)
0xb22d  stloc.s  7
0xb22f  ldloc.s  7
0xb231  brfalse.s loc_B282
0xb233  ldloc.s  7
0xb235  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xb23a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Entity>::get_Count()
0xb23f  ldc.i4.0
0xb240  ble.s    loc_B282
0xb242  ldarg.s  7
0xb244  ldloc.s  7
0xb246  callvirt instance string Microsoft.Xrm.Sdk.EntityCollection::get_PagingCookie()
0xb24b  stind.ref
0xb24c  ldarg.s  8
0xb24e  ldloc.s  7
0xb250  callvirt instance bool Microsoft.Xrm.Sdk.EntityCollection::get_MoreRecords()
0xb255  stind.i1
0xb256  ldloc.s  6
0xb258  ldloc.s  7
0xb25a  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xb25f  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Entity>::get_Count()
0xb264  add
0xb265  stloc.s  6
0xb267  ldloc.s  4
0xb269  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xb26e  ldloc.s  7
0xb270  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xb275  callvirt instance void class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xb27a  ldarg.s  8
0xb27c  ldind.u1
0xb27d  brtrue   loc_B12F
0xb282  ldloc.s  4
0xb284  callvirt instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Entity> Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xb289  stloc.0
0xb28a  ldarg.s  4
0xb28c  brfalse.s loc_B29A
0xb28e  ldarg.0
0xb28f  ldloc.0
0xb290  ldarg.s  4
0xb292  ldarg.s  6
0xb294  call     instance class [mscorlib]System.Collections.IEnumerable Microsoft.Xrm.Sdk.Linq.QueryProvider::ExecuteAnonymousType(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Xrm.Sdk.Entity> entities, class Projection projection, class [mscorlib]System.Collections.Generic.List`1<class LinkLookup> linkLookups)
0xb299  ret
0xb29a  ldloc.0
0xb29b  ldarg.0
0xb29c  ldftn    instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.Linq.QueryProvider::AttachToContext(class Microsoft.Xrm.Sdk.Entity entity)
0xb2a2  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Xrm.Sdk.Entity, class Microsoft.Xrm.Sdk.Entity>::.ctor(object, native int)
0xb2a7  call     T0x2B000029
0xb2ac  stloc.s  0xA
0xb2ae  ldloc.s  0xA
0xb2b0  ret
```
