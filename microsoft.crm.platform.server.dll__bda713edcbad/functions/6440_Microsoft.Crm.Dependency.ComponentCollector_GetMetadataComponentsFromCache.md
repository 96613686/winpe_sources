# Microsoft.Crm.Dependency.ComponentCollector::GetMetadataComponentsFromCache

- ea: `0x6440`
- end: `0x64d3`
- name: `Microsoft.Crm.Dependency.ComponentCollector::GetMetadataComponentsFromCache`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x63c0`

## callees

- `0x6440`
- `0x67030`

## string_xrefs

- `0x648f`: `componentstate`
- `0x649d`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x6440  ldarg.3
0x6441  callvirt instance bool Microsoft.Crm.BusinessEntities.ExecutionContext::get_IsDependencyOptimizationForCdsV2Enabled()
0x6446  brtrue.s loc_644A
0x6448  ldnull
0x6449  ret
0x644a  ldarg.1
0x644b  ldarg.3
0x644c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6451  stloc.0
0x6452  ldarg.3
0x6453  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6458  stloc.1
0x6459  ldloc.1
0x645a  brfalse.s loc_6467
0x645c  ldarg.2
0x645d  brfalse.s loc_6467
0x645f  ldarg.1
0x6460  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6465  brfalse.s loc_6469
0x6467  ldnull
0x6468  ret
0x6469  ldarg.2
0x646a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x646f  stloc.2
0x6470  br.s     loc_64B5
0x6472  ldloca.s 2
0x6474  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x6479  stloc.3
0x647a  ldloc.1
0x647b  ldarg.1
0x647c  ldloc.3
0x647d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetMetadataBusinessEntityFromCache(string, valuetype [mscorlib]System.Guid)
0x6482  stloc.s  4
0x6484  ldloc.s  4
0x6486  brtrue.s loc_648D
0x6488  ldnull
0x6489  stloc.s  5
0x648b  leave.s  loc_64D0
0x648d  ldloc.s  4
0x648f  ldstr    aComponentstate// "componentstate"
0x6494  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x6499  brtrue.s loc_64AD
0x649b  ldloc.s  4
0x649d  ldstr    aComponentstate// "componentstate"
0x64a2  ldc.i4.0
0x64a3  box      [mscorlib]System.Int32
0x64a8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x64ad  ldloc.0
0x64ae  ldloc.s  4
0x64b0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::Add(var<u1>)
0x64b5  ldloca.s 2
0x64b7  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x64bc  brtrue.s loc_6472
0x64be  leave.s  loc_64CE
0x64c0  ldloca.s 2
0x64c2  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x64c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64cd  endfinally
0x64ce  ldloc.0
0x64cf  ret
0x64d0  ldloc.s  5
0x64d2  ret
```
