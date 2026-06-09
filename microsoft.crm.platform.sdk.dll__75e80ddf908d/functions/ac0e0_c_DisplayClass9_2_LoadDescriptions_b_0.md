# <>c__DisplayClass9_2::<LoadDescriptions>b__0

- ea: `0xac0e0`
- end: `0xac253`
- name: `<>c__DisplayClass9_2::<LoadDescriptions>b__0`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x29470`
- `0x51f10`
- `0x53120`
- `0x5b670`
- `0x71090`
- `0x717d0`
- `0xac0e0`

## string_xrefs

- `0xac18a`: `ComponentState`
- `0xac208`: `ComponentState`
- `0xac117`: `We should not receive any component rows with the system solution id if system metadata has already been loaded`

## pseudocode

```c

```

## disassembly

```asm
0xac0e0  br       loc_AC247
0xac0e5  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0xac0ea  ldarg.1
0xac0eb  ldstr    aSolutionid// "SolutionId"
0xac0f0  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xac0f5  unbox.any [mscorlib]System.Guid
0xac0fa  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xac0ff  brfalse  loc_AC189
0xac104  ldarg.0
0xac105  ldfld    class <>c__DisplayClass9_1 <>c__DisplayClass9_2::CS$<>8__locals2
0xac10a  ldfld    class <>c__DisplayClass9_0 <>c__DisplayClass9_1::CS$<>8__locals1
0xac10f  ldfld    bool <>c__DisplayClass9_0::isSystemDataLoaded
0xac114  ldc.i4.0
0xac115  ceq
0xac117  ldstr    aWeShouldNotRec// "We should not receive any component row"...
0xac11c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xac121  ldarg.0
0xac122  ldfld    class <>c__DisplayClass9_1 <>c__DisplayClass9_2::CS$<>8__locals2
0xac127  ldfld    class <>c__DisplayClass9_0 <>c__DisplayClass9_1::CS$<>8__locals1
0xac12c  ldfld    class Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader <>c__DisplayClass9_0::<>4__this
0xac131  ldarg.0
0xac132  ldfld    class <>c__DisplayClass9_1 <>c__DisplayClass9_2::CS$<>8__locals2
0xac137  ldfld    class <>c__DisplayClass9_0 <>c__DisplayClass9_1::CS$<>8__locals1
0xac13c  ldfld    string <>c__DisplayClass9_0::name
0xac141  callvirt instance class Microsoft.Crm.Metadata.IFillableMetadataDescription Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::CreateFillableDescription(string name)
0xac146  stloc.0
0xac147  ldloc.0
0xac148  ldarg.1
0xac149  ldarg.0
0xac14a  ldfld    class <>c__DisplayClass9_1 <>c__DisplayClass9_2::CS$<>8__locals2
0xac14f  ldfld    class <>c__DisplayClass9_0 <>c__DisplayClass9_1::CS$<>8__locals1
0xac154  ldfld    class Microsoft.Crm.Metadata.MetadataForMetadata <>c__DisplayClass9_0::metadataForMetadata
0xac159  callvirt instance void Microsoft.Crm.Metadata.IFillableMetadataDescription::FillPropertiesFromDataReader(class [System.Data]System.Data.IDataReader reader, [opt] class Microsoft.Crm.Metadata.MetadataForMetadata metadataForMetadata)
0xac15e  ldarg.0
0xac15f  ldfld    class <>c__DisplayClass9_1 <>c__DisplayClass9_2::CS$<>8__locals2
0xac164  ldfld    class <>c__DisplayClass9_0 <>c__DisplayClass9_1::CS$<>8__locals1
0xac169  ldfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass9_0::systemContainer
0xac16e  ldloc.0
0xac16f  ldarg.0
0xac170  ldfld    class <>c__DisplayClass9_1 <>c__DisplayClass9_2::CS$<>8__locals2
0xac175  ldfld    class <>c__DisplayClass9_0 <>c__DisplayClass9_1::CS$<>8__locals1
0xac17a  ldfld    string <>c__DisplayClass9_0::name
0xac17f  callvirt instance void Microsoft.Crm.Metadata.MetadataContainer::AddDescription(class Microsoft.Crm.Metadata.IMetadataDescription description, string name)
0xac184  br       loc_AC247
0xac189  ldarg.1
0xac18a  ldstr    aComponentstate_0// "ComponentState"
0xac18f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xac194  unbox.any [mscorlib]System.Byte
0xac199  brtrue.s loc_AC206
0xac19b  ldarg.0
0xac19c  ldfld    class <>c__DisplayClass9_1 <>c__DisplayClass9_2::CS$<>8__locals2
0xac1a1  ldfld    class <>c__DisplayClass9_0 <>c__DisplayClass9_1::CS$<>8__locals1
0xac1a6  ldfld    class Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader <>c__DisplayClass9_0::<>4__this
0xac1ab  ldarg.0
0xac1ac  ldfld    class <>c__DisplayClass9_1 <>c__DisplayClass9_2::CS$<>8__locals2
0xac1b1  ldfld    class <>c__DisplayClass9_0 <>c__DisplayClass9_1::CS$<>8__locals1
0xac1b6  ldfld    string <>c__DisplayClass9_0::name
0xac1bb  call     instance class Microsoft.Crm.Metadata.IFillableMetadataDescription Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::CreateFullDescriptionOverrideByName(string name)
0xac1c0  stloc.1
0xac1c1  ldloc.1
0xac1c2  ldarg.1
0xac1c3  ldarg.0
0xac1c4  ldfld    class <>c__DisplayClass9_1 <>c__DisplayClass9_2::CS$<>8__locals2
0xac1c9  ldfld    class <>c__DisplayClass9_0 <>c__DisplayClass9_1::CS$<>8__locals1
0xac1ce  ldfld    class Microsoft.Crm.Metadata.MetadataForMetadata <>c__DisplayClass9_0::metadataForMetadata
0xac1d3  callvirt instance void Microsoft.Crm.Metadata.IFillableMetadataDescription::FillPropertiesFromDataReader(class [System.Data]System.Data.IDataReader reader, [opt] class Microsoft.Crm.Metadata.MetadataForMetadata metadataForMetadata)
0xac1d8  ldarg.0
0xac1d9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription> <>c__DisplayClass9_2::overrideDescriptions
0xac1de  ldarg.1
0xac1df  ldarg.0
0xac1e0  ldfld    class <>c__DisplayClass9_1 <>c__DisplayClass9_2::CS$<>8__locals2
0xac1e5  ldfld    class Microsoft.Crm.Metadata.MetadataEntityMetadata <>c__DisplayClass9_1::metadataEntity
0xac1ea  callvirt instance class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0xac1ef  callvirt instance string Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_PhysicalName()
0xac1f4  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xac1f9  unbox.any [mscorlib]System.Guid
0xac1fe  ldloc.1
0xac1ff  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.IMetadataDescription>::Add(var<u1>, !!T0)
0xac204  br.s     loc_AC247
0xac206  ldc.i4.2
0xac207  ldarg.1
0xac208  ldstr    aComponentstate_0// "ComponentState"
0xac20d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xac212  unbox.any [mscorlib]System.Byte
0xac217  bne.un.s loc_AC247
0xac219  ldarg.1
0xac21a  ldarg.0
0xac21b  ldfld    class <>c__DisplayClass9_1 <>c__DisplayClass9_2::CS$<>8__locals2
0xac220  ldfld    class Microsoft.Crm.Metadata.MetadataEntityMetadata <>c__DisplayClass9_1::metadataEntity
0xac225  callvirt instance class Microsoft.Crm.Metadata.MetadataAttributeMetadata Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0xac22a  callvirt instance string Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_PhysicalName()
0xac22f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xac234  unbox.any [mscorlib]System.Guid
0xac239  stloc.2
0xac23a  ldarg.0
0xac23b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool> <>c__DisplayClass9_2::idsToDelete
0xac240  ldloc.2
0xac241  ldc.i4.1
0xac242  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>::Add(var<u1>, !!T0)
0xac247  ldarg.1
0xac248  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xac24d  brtrue   loc_AC0E5
0xac252  ret
```
