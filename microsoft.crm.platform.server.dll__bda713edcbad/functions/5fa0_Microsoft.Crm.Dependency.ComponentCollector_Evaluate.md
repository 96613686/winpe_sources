# Microsoft.Crm.Dependency.ComponentCollector::Evaluate

- ea: `0x5fa0`
- end: `0x62b6`
- name: `Microsoft.Crm.Dependency.ComponentCollector::Evaluate`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x5e70`

## callees

- `0x5fa0`
- `0x62c0`
- `0x63c0`
- `0x64e0`
- `0x68f0`
- `0x6a20`
- `0x6a40`
- `0x6a60`
- `0x75a0`
- `0x66ae0`
- `0x7e1c0`

## string_xrefs

- `0x5ffa`: `componentstate`
- `0x60d2`: `componentstate`
- `0x6241`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x5fa0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::Instance()
0x5fa5  ldarg.s  4
0x5fa7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5fac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x5fb1  ldarg.s  4
0x5fb3  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution>::LookupEntry(void, var<u1>)
0x5fb8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_IsProtected()
0x5fbd  brfalse.s loc_5FCD
0x5fbf  ldarg.s  4
0x5fc1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x5fc6  call     bool Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInUpgradeOrSystemConvertedSolutionUpgradeContext(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x5fcb  br.s     loc_5FCE
0x5fcd  ldc.i4.0
0x5fce  stloc.0
0x5fcf  ldarg.1
0x5fd0  call     bool Microsoft.Crm.Solution.SolutionComponentTypeMap::IsMetadata(int32 componentType)
0x5fd5  brfalse  loc_614E
0x5fda  ldarg.0
0x5fdb  ldarg.1
0x5fdc  ldarg.3
0x5fdd  ldc.i4.0
0x5fde  ldarg.s  4
0x5fe0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Dependency.ComponentCollector::MetadataComponentRetrieval(int32 componentType, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> ids, bool retrieveUnpublished, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5fe5  stloc.1
0x5fe6  ldloc.1
0x5fe7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x5fec  stloc.2
0x5fed  br       loc_6088
0x5ff2  ldloc.2
0x5ff3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x5ff8  stloc.3
0x5ff9  ldloc.3
0x5ffa  ldstr    aComponentstate// "componentstate"
0x5fff  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x6004  unbox.any [mscorlib]System.Int32
0x6009  brtrue.s loc_6088
0x600b  ldarg.2
0x600c  ldloc.3
0x600d  ldloc.3
0x600e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x6013  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x6018  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x601d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x6022  unbox.any [mscorlib]System.Guid
0x6027  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Item(void)
0x602c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::GetEnumerator()
0x6031  stloc.s  4
0x6033  br.s     loc_606F
0x6035  ldloca.s 4
0x6037  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::get_Current()
0x603c  stloc.s  5
0x603e  ldloc.s  5
0x6040  ldloc.3
0x6041  callvirt instance void Microsoft.Crm.Dependency.ComponentCollectorRecord::set_Entity(object value)
0x6046  ldarg.s  5
0x6048  brfalse.s loc_606F
0x604a  ldarg.s  5
0x604c  ldloc.s  5
0x604e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Dependency.ComponentCollectorRecord::get_ComponentId()
0x6053  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection>::ContainsKey(var<u1>)
0x6058  brfalse.s loc_606F
0x605a  ldloc.s  5
0x605c  ldarg.s  5
0x605e  ldloc.s  5
0x6060  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Dependency.ComponentCollectorRecord::get_ComponentId()
0x6065  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection>::get_Item(void)
0x606a  callvirt instance void Microsoft.Crm.Dependency.ComponentCollectorRecord::set_PreviousInvalidDependencies(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection value)
0x606f  ldloca.s 4
0x6071  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::MoveNext()
0x6076  brtrue.s loc_6035
0x6078  leave.s  loc_6088
0x607a  ldloca.s 4
0x607c  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>
0x6082  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6087  endfinally
0x6088  ldloc.2
0x6089  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x608e  brtrue   loc_5FF2
0x6093  leave.s  loc_609F
0x6095  ldloc.2
0x6096  brfalse.s loc_609E
0x6098  ldloc.2
0x6099  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x609e  endfinally
0x609f  ldloc.1
0x60a0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection::get_MetadataEntity()
0x60a5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_IsPublishable()
0x60aa  brfalse  loc_62B5
0x60af  ldloc.0
0x60b0  brtrue   loc_62B5
0x60b5  ldarg.0
0x60b6  ldarg.1
0x60b7  ldarg.3
0x60b8  ldc.i4.1
0x60b9  ldarg.s  4
0x60bb  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Dependency.ComponentCollector::MetadataComponentRetrieval(int32 componentType, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> ids, bool retrieveUnpublished, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x60c0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x60c5  stloc.2
0x60c6  br.s     loc_6137
0x60c8  ldloc.2
0x60c9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x60ce  stloc.s  6
0x60d0  ldloc.s  6
0x60d2  ldstr    aComponentstate// "componentstate"
0x60d7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x60dc  unbox.any [mscorlib]System.Int32
0x60e1  ldc.i4.1
0x60e2  bne.un.s loc_6137
0x60e4  ldarg.2
0x60e5  ldloc.s  6
0x60e7  ldloc.s  6
0x60e9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x60ee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x60f3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x60f8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x60fd  unbox.any [mscorlib]System.Guid
0x6102  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Item(void)
0x6107  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::GetEnumerator()
0x610c  stloc.s  4
0x610e  br.s     loc_611E
0x6110  ldloca.s 4
0x6112  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::get_Current()
0x6117  ldloc.s  6
0x6119  callvirt instance void Microsoft.Crm.Dependency.ComponentCollectorRecord::set_UnpublishedEntity(object value)
0x611e  ldloca.s 4
0x6120  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::MoveNext()
0x6125  brtrue.s loc_6110
0x6127  leave.s  loc_6137
0x6129  ldloca.s 4
0x612b  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>
0x6131  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6136  endfinally
0x6137  ldloc.2
0x6138  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x613d  brtrue.s loc_60C8
0x613f  leave    loc_62B5
0x6144  ldloc.2
0x6145  brfalse.s loc_614D
0x6147  ldloc.2
0x6148  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x614d  endfinally
0x614e  ldarg.0
0x614f  ldarg.1
0x6150  ldarg.3
0x6151  ldc.i4.0
0x6152  ldarg.s  4
0x6154  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Dependency.ComponentCollector::ComponentRetrieval(int32 componentType, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> ids, bool retrieveUnpublished, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6159  stloc.s  7
0x615b  ldloc.s  7
0x615d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x6162  stloc.s  8
0x6164  br.s     loc_61E3
0x6166  ldloc.s  8
0x6168  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x616d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x6172  stloc.s  9
0x6174  ldarg.0
0x6175  ldloc.s  9
0x6177  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Dependency.ComponentCollector::GetPrimaryKeyFromEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity)
0x617c  stloc.s  0xA
0x617e  ldarg.2
0x617f  ldloc.s  0xA
0x6181  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Item(void)
0x6186  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::GetEnumerator()
0x618b  stloc.s  4
0x618d  br.s     loc_61CA
0x618f  ldloca.s 4
0x6191  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::get_Current()
0x6196  stloc.s  0xB
0x6198  ldloc.s  0xB
0x619a  ldloc.s  9
0x619c  callvirt instance void Microsoft.Crm.Dependency.ComponentCollectorRecord::set_Entity(object value)
0x61a1  ldarg.s  5
0x61a3  brfalse.s loc_61CA
0x61a5  ldarg.s  5
0x61a7  ldloc.s  0xB
0x61a9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Dependency.ComponentCollectorRecord::get_ComponentId()
0x61ae  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection>::ContainsKey(var<u1>)
0x61b3  brfalse.s loc_61CA
0x61b5  ldloc.s  0xB
0x61b7  ldarg.s  5
0x61b9  ldloc.s  0xB
0x61bb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Dependency.ComponentCollectorRecord::get_ComponentId()
0x61c0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection>::get_Item(void)
0x61c5  callvirt instance void Microsoft.Crm.Dependency.ComponentCollectorRecord::set_PreviousInvalidDependencies(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection value)
0x61ca  ldloca.s 4
0x61cc  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::MoveNext()
0x61d1  brtrue.s loc_618F
0x61d3  leave.s  loc_61E3
0x61d5  ldloca.s 4
0x61d7  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>
0x61dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61e2  endfinally
0x61e3  ldloc.s  8
0x61e5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x61ea  brtrue   loc_6166
0x61ef  leave.s  loc_6206
0x61f1  ldloc.s  8
0x61f3  isinst   [mscorlib]System.IDisposable
0x61f8  stloc.s  0xC
0x61fa  ldloc.s  0xC
0x61fc  brfalse.s loc_6205
0x61fe  ldloc.s  0xC
0x6200  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6205  endfinally
0x6206  ldloc.s  7
0x6208  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_EntityMetadata()
0x620d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsPublishable()
0x6212  brfalse  loc_62B5
0x6217  ldloc.0
0x6218  brtrue   loc_62B5
0x621d  ldarg.0
0x621e  ldarg.1
0x621f  ldarg.3
0x6220  ldc.i4.1
0x6221  ldarg.s  4
0x6223  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Dependency.ComponentCollector::ComponentRetrieval(int32 componentType, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> ids, bool retrieveUnpublished, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6228  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x622d  stloc.s  8
0x622f  br.s     loc_6295
0x6231  ldloc.s  8
0x6233  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6238  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x623d  stloc.s  0xD
0x623f  ldloc.s  0xD
0x6241  ldstr    aComponentstate// "componentstate"
0x6246  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x624b  unbox.any [mscorlib]System.Int32
0x6250  ldc.i4.1
0x6251  bne.un.s loc_6295
0x6253  ldarg.0
0x6254  ldloc.s  0xD
0x6256  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Dependency.ComponentCollector::GetPrimaryKeyFromEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity)
0x625b  stloc.s  0xE
0x625d  ldarg.2
0x625e  ldloc.s  0xE
0x6260  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Dependency.ComponentCollectorRecordCollection>::get_Item(void)
0x6265  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::GetEnumerator()
0x626a  stloc.s  4
0x626c  br.s     loc_627C
0x626e  ldloca.s 4
0x6270  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::get_Current()
0x6275  ldloc.s  0xD
0x6277  callvirt instance void Microsoft.Crm.Dependency.ComponentCollectorRecord::set_UnpublishedEntity(object value)
0x627c  ldloca.s 4
0x627e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>::MoveNext()
0x6283  brtrue.s loc_626E
0x6285  leave.s  loc_6295
0x6287  ldloca.s 4
0x6289  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Dependency.ComponentCollectorRecord>
0x628f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6294  endfinally
0x6295  ldloc.s  8
0x6297  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x629c  brtrue.s loc_6231
0x629e  leave.s  loc_62B5
0x62a0  ldloc.s  8
0x62a2  isinst   [mscorlib]System.IDisposable
0x62a7  stloc.s  0xC
0x62a9  ldloc.s  0xC
0x62ab  brfalse.s loc_62B4
0x62ad  ldloc.s  0xC
0x62af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62b4  endfinally
0x62b5  ret
```
