# Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetData

- ea: `0xc6330`
- end: `0xc64ec`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetData`
- size: `444`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xc6330`
- `0xc85c0`

## string_xrefs

- `0xc6483`: `componenttype`
- `0xc647b`: `solutioncomponentid`
- `0xc6347`: `componentTypeFilter`
- `0xc6382`: `componentTypeFilter`

## pseudocode

```c

```

## disassembly

```asm
0xc6330  ldarg.0
0xc6331  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc6336  ldstr    aSolutionid// "solutionid"
0xc633b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc6340  stloc.0
0xc6341  ldarg.0
0xc6342  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc6347  ldstr    aComponenttypef// "componentTypeFilter"
0xc634c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc6351  stloc.1
0xc6352  ldloc.1
0xc6353  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.ComponentTypeSubcode::IsStringContainsSubcode(string)
0xc6358  brfalse.s loc_C6372
0xc635a  ldloc.1
0xc635b  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.ComponentTypeSubcode::GetComponentTypeFromString(string)
0xc6360  ldc.i4.s 0x3C
0xc6362  bne.un.s loc_C6372
0xc6364  ldloc.1
0xc6365  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Utility.ComponentTypeSubcode::GetSubcomponentNumberFromString(string)
0xc636a  ldc.i4.1
0xc636b  bne.un.s loc_C6372
0xc636d  ldc.i4.s 0x3C
0xc636f  stloc.2
0xc6370  br.s     loc_C6397
0xc6372  ldtoken  [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter
0xc6377  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc637c  ldarg.0
0xc637d  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc6382  ldstr    aComponenttypef// "componentTypeFilter"
0xc6387  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc638c  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0xc6391  unbox.any [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.ComponentTypeFilter
0xc6396  stloc.2
0xc6397  ldarg.0
0xc6398  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc639d  ldstr    aEntitydashboar// "entitydashboardCode"
0xc63a2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc63a7  brfalse.s loc_C63D4
0xc63a9  ldarg.0
0xc63aa  ldarg.0
0xc63ab  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0xc63b0  ldstr    aEntitydashboar// "entitydashboardCode"
0xc63b5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc63ba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc63bf  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xc63c4  stfld    int32 Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::ObjType
0xc63c9  ldarg.0
0xc63ca  ldstr    aEntitydashboar_0// "entityDashboard"
0xc63cf  stfld    string Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::ReqType
0xc63d4  ldarg.0
0xc63d5  ldloc.0
0xc63d6  ldloc.2
0xc63d7  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>> Microsoft.Crm.Application.Controls.SystemCustomization.SolutionComponentsGridDataProvider::GetSolutionComponentsRows(string solutionId, int32 componentType)
0xc63dc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Row>::.ctor()
0xc63e1  stloc.3
0xc63e2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::get_Values()
0xc63e7  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::GetEnumerator()
0xc63ec  stloc.s  4
0xc63ee  br.s     loc_C6428
0xc63f0  ldloca.s 4
0xc63f2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::get_Current()
0xc63f7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Row>::GetEnumerator()
0xc63fc  stloc.s  5
0xc63fe  br.s     loc_C6411
0xc6400  ldloc.s  5
0xc6402  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Row>::get_Current()
0xc6407  stloc.s  6
0xc6409  ldloc.3
0xc640a  ldloc.s  6
0xc640c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Row>::Add(var<u1>)
0xc6411  ldloc.s  5
0xc6413  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc6418  brtrue.s loc_C6400
0xc641a  leave.s  loc_C6428
0xc641c  ldloc.s  5
0xc641e  brfalse.s loc_C6427
0xc6420  ldloc.s  5
0xc6422  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc6427  endfinally
0xc6428  ldloca.s 4
0xc642a  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>::MoveNext()
0xc642f  brtrue.s loc_C63F0
0xc6431  leave.s  loc_C6441
0xc6433  ldloca.s 4
0xc6435  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<int32, class [mscorlib]System.Collections.Generic.IList`1<class Row>>
0xc643b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc6440  endfinally
0xc6441  ldarg.1
0xc6442  ldc.i4.s 0x12
0xc6444  newarr   [mscorlib]System.String
0xc6449  dup
0xc644a  ldc.i4.0
0xc644b  ldstr    aOid// "oid"
0xc6450  stelem.ref
0xc6451  dup
0xc6452  ldc.i4.1
0xc6453  ldstr    aMoid// "moid"
0xc6458  stelem.ref
0xc6459  dup
0xc645a  ldc.i4.2
0xc645b  ldstr    aDisplayname// "displayname"
0xc6460  stelem.ref
0xc6461  dup
0xc6462  ldc.i4.3
0xc6463  ldstr    aName// "name"
0xc6468  stelem.ref
0xc6469  dup
0xc646a  ldc.i4.4
0xc646b  ldstr    aType// "type"
0xc6470  stelem.ref
0xc6471  dup
0xc6472  ldc.i4.5
0xc6473  ldstr    aDescription// "description"
0xc6478  stelem.ref
0xc6479  dup
0xc647a  ldc.i4.6
0xc647b  ldstr    aSolutioncompon_0// "solutioncomponentid"
0xc6480  stelem.ref
0xc6481  dup
0xc6482  ldc.i4.7
0xc6483  ldstr    aComponenttype// "componenttype"
0xc6488  stelem.ref
0xc6489  dup
0xc648a  ldc.i4.8
0xc648b  ldstr    aSubtype// "subtype"
0xc6490  stelem.ref
0xc6491  dup
0xc6492  ldc.i4.s 9
0xc6494  ldstr    aIsmanaged// "ismanaged"
0xc6499  stelem.ref
0xc649a  dup
0xc649b  ldc.i4.s 0xA
0xc649d  ldstr    aIscustomizable// "iscustomizable"
0xc64a2  stelem.ref
0xc64a3  dup
0xc64a4  ldc.i4.s 0xB
0xc64a6  ldstr    aOtc// "otc"
0xc64ab  stelem.ref
0xc64ac  dup
0xc64ad  ldc.i4.s 0xC
0xc64af  ldstr    aIsauditenabled// "isauditenabled"
0xc64b4  stelem.ref
0xc64b5  dup
0xc64b6  ldc.i4.s 0xD
0xc64b8  ldstr    aSchemaname// "schemaname"
0xc64bd  stelem.ref
0xc64be  dup
0xc64bf  ldc.i4.s 0xE
0xc64c1  ldstr    aCategory// "category"
0xc64c6  stelem.ref
0xc64c7  dup
0xc64c8  ldc.i4.s 0xF
0xc64ca  ldstr    aIstabletenable// "istabletenabled"
0xc64cf  stelem.ref
0xc64d0  dup
0xc64d1  ldc.i4.s 0x10
0xc64d3  ldstr    aSynctoexternal// "synctoexternalsearchindex"
0xc64d8  stelem.ref
0xc64d9  dup
0xc64da  ldc.i4.s 0x11
0xc64dc  ldstr    aIsappaware// "isappaware"
0xc64e1  stelem.ref
0xc64e2  stind.ref
0xc64e3  ldarg.2
0xc64e4  ldloc.3
0xc64e5  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Row>::ToArray()
0xc64ea  stind.ref
0xc64eb  ret
```
