# Microsoft.Crm.ObjectModel.ExternalSearch.ExternalSearchService::ParseEntityFilters

- ea: `0x20a290`
- end: `0x20a50b`
- name: `Microsoft.Crm.ObjectModel.ExternalSearch.ExternalSearchService::ParseEntityFilters`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x209bd0`

## callees

- `0x20a290`
- `0x20a510`
- `0x20a5f0`
- `0x20af60`

## string_xrefs

- `0x20a3bd`: `Common Attributes`
- `0x20a472`: `Common Attributes`
- `0x20a482`: `Common Attributes`
- `0x20a4a3`: `Common Attributes`
- `0x20a4bd`: `Common Attributes`
- `0x20a4dc`: `Common Attributes`
- `0x20a4fe`: `Common Attributes`

## pseudocode

```c

```

## disassembly

```asm
0x20a290  ldarg.3
0x20a291  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x20a296  brfalse.s loc_20A29A
0x20a298  ldnull
0x20a299  ret
0x20a29a  ldarg.3
0x20a29b  callvirt instance string [mscorlib]System.String::Trim()
0x20a2a0  starg.s  3
0x20a2a2  ldarg.2
0x20a2a3  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x20a2a8  brtrue.s loc_20A2AC
0x20a2aa  ldnull
0x20a2ab  ret
0x20a2ac  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x20a2b1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x20a2b6  stloc.0
0x20a2b7  ldarg.2
0x20a2b8  ldc.i4.0
0x20a2b9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<string>::get_Item(!!T0)
0x20a2be  ldstr    aActivitymimeat_3// "activitymimeattachment"
0x20a2c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x20a2c8  brfalse.s loc_20A2D3
0x20a2ca  ldarg.2
0x20a2cb  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x20a2d0  ldc.i4.1
0x20a2d1  bgt.s    loc_20A2DC
0x20a2d3  ldarg.2
0x20a2d4  ldc.i4.0
0x20a2d5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<string>::get_Item(!!T0)
0x20a2da  br.s     loc_20A2E3
0x20a2dc  ldarg.2
0x20a2dd  ldc.i4.1
0x20a2de  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<string>::get_Item(!!T0)
0x20a2e3  stloc.1
0x20a2e4  ldarg.1
0x20a2e5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x20a2ea  ldloc.1
0x20a2eb  ldc.i4.1
0x20a2ec  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x20a2f1  stloc.2
0x20a2f2  ldarg.3
0x20a2f3  ldc.i4.1
0x20a2f4  newarr   [mscorlib]System.Char
0x20a2f9  dup
0x20a2fa  ldc.i4.0
0x20a2fb  ldc.i4.s 0x2C
0x20a2fd  stelem.i2
0x20a2fe  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x20a303  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__23_0
0x20a308  dup
0x20a309  brtrue.s loc_20A322
0x20a30b  pop
0x20a30c  ldsfld   class <>c <>c::<>9
0x20a311  ldftn    instance string <>c::<ParseEntityFilters>b__23_0(string p)
0x20a317  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x20a31c  dup
0x20a31d  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__23_0
0x20a322  call     T0x2B0000FF
0x20a327  call     T0x2B000087
0x20a32c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x20a331  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x20a336  stloc.3
0x20a337  br       loc_20A44E
0x20a33c  ldloc.3
0x20a33d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x20a342  stloc.s  4
0x20a344  ldloc.s  4
0x20a346  ldc.i4.s 0x20
0x20a348  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x20a34d  stloc.s  5
0x20a34f  ldloc.s  5
0x20a351  ldc.i4.m1
0x20a352  bne.un.s loc_20A364
0x20a354  ldarg.s  4
0x20a356  ldloc.1
0x20a357  ldloc.s  4
0x20a359  ldarg.1
0x20a35a  call     void Microsoft.Crm.ObjectModel.ExternalSearch.ExternalSearchService::TraceWrongFilter(class [mscorlib]System.Collections.Generic.List`1<string> warningList, string defaultEntity, string filterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x20a35f  br       loc_20A44E
0x20a364  ldloc.s  4
0x20a366  ldc.i4.0
0x20a367  ldloc.s  5
0x20a369  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x20a36e  ldc.i4.1
0x20a36f  newarr   [mscorlib]System.Char
0x20a374  dup
0x20a375  ldc.i4.0
0x20a376  ldc.i4.s 0x3A
0x20a378  stelem.i2
0x20a379  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x20a37e  stloc.s  6
0x20a380  ldloc.s  6
0x20a382  ldlen
0x20a383  conv.i4
0x20a384  ldc.i4.1
0x20a385  beq.s    loc_20A391
0x20a387  ldloc.s  6
0x20a389  ldlen
0x20a38a  conv.i4
0x20a38b  ldc.i4.2
0x20a38c  bne.un   loc_20A443
0x20a391  ldloc.s  6
0x20a393  ldlen
0x20a394  conv.i4
0x20a395  ldc.i4.1
0x20a396  beq.s    loc_20A3AC
0x20a398  ldloc.s  4
0x20a39a  ldloc.s  4
0x20a39c  ldc.i4.s 0x3A
0x20a39e  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x20a3a3  ldc.i4.1
0x20a3a4  add
0x20a3a5  callvirt instance string [mscorlib]System.String::Substring(int32)
0x20a3aa  br.s     loc_20A3AE
0x20a3ac  ldloc.s  4
0x20a3ae  stloc.s  7
0x20a3b0  ldloc.s  6
0x20a3b2  ldlen
0x20a3b3  conv.i4
0x20a3b4  ldc.i4.1
0x20a3b5  beq.s    loc_20A3BD
0x20a3b7  ldloc.s  6
0x20a3b9  ldc.i4.0
0x20a3ba  ldelem.ref
0x20a3bb  br.s     loc_20A3C2
0x20a3bd  ldstr    aCommonAttribut// "Common Attributes"
0x20a3c2  stloc.s  8
0x20a3c4  ldloc.s  6
0x20a3c6  ldlen
0x20a3c7  conv.i4
0x20a3c8  ldc.i4.1
0x20a3c9  beq.s    loc_20A3EE
0x20a3cb  ldloc.s  8
0x20a3cd  callvirt instance string [mscorlib]System.String::ToLower()
0x20a3d2  ldstr    aActivities_0// "activities"
0x20a3d7  callvirt instance bool [mscorlib]System.String::Equals(string)
0x20a3dc  brtrue.s loc_20A3EE
0x20a3de  ldarg.1
0x20a3df  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x20a3e4  ldloc.s  8
0x20a3e6  ldc.i4.1
0x20a3e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x20a3ec  br.s     loc_20A3EF
0x20a3ee  ldloc.2
0x20a3ef  stloc.s  9
0x20a3f1  ldloc.s  9
0x20a3f3  brtrue.s loc_20A40C
0x20a3f5  ldloc.2
0x20a3f6  stloc.s  9
0x20a3f8  ldstr    aFilterQueryFor// "Filter query for '{0}' could not be pro"...
0x20a3fd  ldloc.s  8
0x20a3ff  call     string [mscorlib]System.String::Format(string, object)
0x20a404  ldarg.s  4
0x20a406  ldarg.1
0x20a407  call     void Microsoft.Crm.ObjectModel.ExternalSearch.ExternalSearchService::TraceError(string message, class [mscorlib]System.Collections.Generic.List`1<string> warningList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x20a40c  ldarg.1
0x20a40d  ldloc.s  9
0x20a40f  ldloc.s  7
0x20a411  call     string Microsoft.Crm.ObjectModel.ExternalSearch.ExternalSearchService::ProcessDateTimeValuesInFilterQuery(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, string filterQuery)
0x20a416  stloc.s  0xA
0x20a418  ldloc.s  0xA
0x20a41a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x20a41f  brtrue.s loc_20A42D
0x20a421  ldloc.0
0x20a422  ldloc.s  8
0x20a424  ldloc.s  0xA
0x20a426  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x20a42b  br.s     loc_20A44E
0x20a42d  ldstr    aErrorOccuredWh_5// "Error occured while converting DateTime"...
0x20a432  ldloc.s  8
0x20a434  call     string [mscorlib]System.String::Format(string, object)
0x20a439  ldarg.s  4
0x20a43b  ldarg.1
0x20a43c  call     void Microsoft.Crm.ObjectModel.ExternalSearch.ExternalSearchService::TraceError(string message, class [mscorlib]System.Collections.Generic.List`1<string> warningList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x20a441  br.s     loc_20A44E
0x20a443  ldarg.s  4
0x20a445  ldloc.1
0x20a446  ldloc.s  4
0x20a448  ldarg.1
0x20a449  call     void Microsoft.Crm.ObjectModel.ExternalSearch.ExternalSearchService::TraceWrongFilter(class [mscorlib]System.Collections.Generic.List`1<string> warningList, string defaultEntity, string filterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x20a44e  ldloc.3
0x20a44f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20a454  brtrue   loc_20A33C
0x20a459  leave.s  loc_20A465
0x20a45b  ldloc.3
0x20a45c  brfalse.s loc_20A464
0x20a45e  ldloc.3
0x20a45f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20a464  endfinally
0x20a465  ldarg.2
0x20a466  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x20a46b  ldc.i4.1
0x20a46c  bne.un   loc_20A509
0x20a471  ldloc.0
0x20a472  ldstr    aCommonAttribut// "Common Attributes"
0x20a477  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x20a47c  brfalse  loc_20A509
0x20a481  ldloc.0
0x20a482  ldstr    aCommonAttribut// "Common Attributes"
0x20a487  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x20a48c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x20a491  brtrue.s loc_20A509
0x20a493  ldloc.0
0x20a494  ldarg.2
0x20a495  ldc.i4.0
0x20a496  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<string>::get_Item(!!T0)
0x20a49b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x20a4a0  brfalse.s loc_20A4B4
0x20a4a2  ldloc.0
0x20a4a3  ldstr    aCommonAttribut// "Common Attributes"
0x20a4a8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x20a4ad  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x20a4b2  brfalse.s loc_20A4CE
0x20a4b4  ldloc.0
0x20a4b5  ldarg.2
0x20a4b6  ldc.i4.0
0x20a4b7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<string>::get_Item(!!T0)
0x20a4bc  ldloc.0
0x20a4bd  ldstr    aCommonAttribut// "Common Attributes"
0x20a4c2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x20a4c7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x20a4cc  br.s     loc_20A4FD
0x20a4ce  ldloc.0
0x20a4cf  ldarg.2
0x20a4d0  ldc.i4.0
0x20a4d1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<string>::get_Item(!!T0)
0x20a4d6  ldstr    a0And1// "({0}) and ({1})"
0x20a4db  ldloc.0
0x20a4dc  ldstr    aCommonAttribut// "Common Attributes"
0x20a4e1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x20a4e6  ldloc.0
0x20a4e7  ldarg.2
0x20a4e8  ldc.i4.0
0x20a4e9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<string>::get_Item(!!T0)
0x20a4ee  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x20a4f3  call     string [mscorlib]System.String::Format(string, object, object)
0x20a4f8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x20a4fd  ldloc.0
0x20a4fe  ldstr    aCommonAttribut// "Common Attributes"
0x20a503  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Remove(var<u1>)
0x20a508  pop
0x20a509  ldloc.0
0x20a50a  ret
```
