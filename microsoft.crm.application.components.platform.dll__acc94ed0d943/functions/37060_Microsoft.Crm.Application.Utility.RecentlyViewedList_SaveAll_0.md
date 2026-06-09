# Microsoft.Crm.Application.Utility.RecentlyViewedList::SaveAll_0

- ea: `0x37060`
- end: `0x37187`
- name: `Microsoft.Crm.Application.Utility.RecentlyViewedList::SaveAll_0`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x36fd0`
- `0x37560`

## callees

- `0x36790`
- `0x36b90`
- `0x36c00`
- `0x36e40`
- `0x36eb0`
- `0x37060`
- `0x37190`
- `0x47920`
- `0x47940`

## string_xrefs

- `0x37097`: `Error Loading the RecentlyViewedXml: {0}`
- `0x3715f`: `Error Loading the RecentlyViewedXml: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x37060  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::.ctor()
0x37065  stloc.0
0x37066  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::.ctor()
0x3706b  stloc.1
0x3706c  ldarg.0
0x3706d  ldarg.s  4
0x3706f  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity> Microsoft.Crm.Application.Utility.RecentlyViewedList::LoadAllInternal(class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx context, class [mscorlib]System.Collections.Generic.ICollection`1<int32> etcList)
0x37074  stloc.2
0x37075  ldarg.1
0x37076  ldarg.0
0x37077  ldloc.2
0x37078  ldarg.2
0x37079  ldarg.3
0x3707a  call     bool Microsoft.Crm.Application.Utility.RecentlyViewedList::ExtractRecentlyViewedFromEntityCollection(class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx context, class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity> entityList, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> recordList, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> viewList)
0x3707f  or
0x37080  starg.s  1
0x37082  leave.s  loc_370C4
0x37084  stloc.s  4
0x37086  ldloc.s  4
0x37088  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x3708d  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x37092  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37097  ldstr    aErrorLoadingTh_1// "Error Loading the RecentlyViewedXml: {0"...
0x3709c  ldc.i4.1
0x3709d  newarr   [mscorlib]System.Object
0x370a2  dup
0x370a3  ldc.i4.0
0x370a4  ldloc.s  4
0x370a6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x370ab  stelem.ref
0x370ac  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x370b1  ldc.i4.0
0x370b2  newarr   [mscorlib]System.Object
0x370b7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x370bc  ldloc.2
0x370bd  call     void Microsoft.Crm.Application.Utility.RecentlyViewedList::ClearRecentlyViewedData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity> entityList)
0x370c2  leave.s  loc_370C4
0x370c4  ldloc.1
0x370c5  ldarg.3
0x370c6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x370cb  ldloc.0
0x370cc  ldarg.2
0x370cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x370d2  ldloc.1
0x370d3  ldloc.0
0x370d4  ldarg.1
0x370d5  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>> Microsoft.Crm.Application.Utility.RecentlyViewedList::MergeClientAndServerData(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> viewList, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> entityList, bool dataChanged)
0x370da  stloc.3
0x370db  ldloc.2
0x370dc  call     void Microsoft.Crm.Application.Utility.RecentlyViewedList::ClearRecentlyViewedData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity> entityList)
0x370e1  ldloc.3
0x370e2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>>::get_Values()
0x370e7  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<int32, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>>::GetEnumerator()
0x370ec  stloc.s  5
0x370ee  br.s     loc_37131
0x370f0  ldloca.s 5
0x370f2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>>::get_Current()
0x370f7  stloc.s  6
0x370f9  ldloc.s  6
0x370fb  brfalse.s loc_37131
0x370fd  ldloc.s  6
0x370ff  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::get_Count()
0x37104  ldc.i4.0
0x37105  ble.s    loc_37131
0x37107  ldloc.s  6
0x37109  ldc.i4.0
0x3710a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>::get_Item(!!T0)
0x3710f  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_EntityTypeCode()
0x37114  stloc.s  7
0x37116  ldloc.s  7
0x37118  ldloc.s  6
0x3711a  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Application.Utility.RecentlyViewedList::ConvertToXml(int32 etc, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord> recordList)
0x3711f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x37124  stloc.s  8
0x37126  ldarg.0
0x37127  ldloc.s  7
0x37129  ldloc.s  8
0x3712b  ldloc.2
0x3712c  call     void Microsoft.Crm.Application.Utility.RecentlyViewedList::SaveInternal(class [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx context, int32 typeCode, string recentlyViewedXml, class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity> entityList)
0x37131  ldloca.s 5
0x37133  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>>::MoveNext()
0x37138  brtrue.s loc_370F0
0x3713a  leave.s  loc_3714A
0x3713c  ldloca.s 5
0x3713e  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.Server.IRecentlyViewedRecord>>
0x37144  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37149  endfinally
0x3714a  leave.s  loc_37186
0x3714c  stloc.s  9
0x3714e  ldloc.s  9
0x37150  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x37155  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x3715a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3715f  ldstr    aErrorLoadingTh_1// "Error Loading the RecentlyViewedXml: {0"...
0x37164  ldc.i4.1
0x37165  newarr   [mscorlib]System.Object
0x3716a  dup
0x3716b  ldc.i4.0
0x3716c  ldloc.s  9
0x3716e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x37173  stelem.ref
0x37174  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x37179  ldc.i4.0
0x3717a  newarr   [mscorlib]System.Object
0x3717f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x37184  leave.s  loc_37186
0x37186  ret
```
