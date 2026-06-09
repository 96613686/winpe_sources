# Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::.cctor

- ea: `0x5d090`
- end: `0x5d575`
- name: `Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::.cctor`
- size: `1253`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xac3d0`

## string_xrefs

- `0x5d4a1`: `Privilege`
- `0x5d4b8`: `Privilege`
- `0x5d4cf`: `Privilege`
- `0x5d4e6`: `PrivilegeObjectTypeCode`
- `0x5d4fd`: `PrivilegeObjectTypeCode`
- `0x5d514`: `PrivilegeObjectTypeCode`
- `0x5d52b`: `RoleTemplatePrivilege`
- `0x5d542`: `RoleTemplatePrivilege`
- `0x5d559`: `RoleTemplatePrivilege`
- `0x5d4ad`: `select {0} from Privilege priv left outer join PrivilegeObjectTypeCodes x on (priv.PrivilegeId = x.PrivilegeId)`
- `0x5d4c4`: `select {0} from Privilege priv left outer join PrivilegeObjectTypeCodes x on (priv.PrivilegeId = x.PrivilegeId)`
- `0x5d4db`: `select {0} from Privilege priv left outer join PrivilegeObjectTypeCodes x on (priv.PrivilegeId = x.PrivilegeId)`
- `0x5d4f2`: `select {0} from PrivilegeObjectTypeCodes x`
- `0x5d509`: `select {0} from PrivilegeObjectTypeCodes x`
- `0x5d520`: `select {0} from PrivilegeObjectTypeCodes x`
- `0x5d537`: `select {0} from RoleTemplatePrivileges x`
- `0x5d54e`: `select {0} from RoleTemplatePrivileges x`
- `0x5d565`: `select {0} from RoleTemplatePrivileges x`

## pseudocode

```c

```

## disassembly

```asm
0x5d090  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::.ctor()
0x5d095  dup
0x5d096  ldstr    aOptionset_0// "OptionSet"
0x5d09b  ldc.i4.1
0x5d09c  ldc.i4.0
0x5d09d  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d0a2  ldstr    aSelect0FromOpt_0// "select {0} from OptionSetAsIfPublishedV"...
0x5d0a7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d0ac  dup
0x5d0ad  ldstr    aOptionset_0// "OptionSet"
0x5d0b2  ldc.i4.0
0x5d0b3  ldc.i4.0
0x5d0b4  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d0b9  ldstr    aSelect0FromOpt_1// "select {0} from OptionSetView x"
0x5d0be  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d0c3  dup
0x5d0c4  ldstr    aOptionset_0// "OptionSet"
0x5d0c9  ldc.i4.0
0x5d0ca  ldc.i4.1
0x5d0cb  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d0d0  ldstr    aSelect0FromOpt_2// "select {0} from OptionSetAsIfStagedView"...
0x5d0d5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d0da  dup
0x5d0db  ldstr    aEntity_0// "Entity"
0x5d0e0  ldc.i4.0
0x5d0e1  ldc.i4.0
0x5d0e2  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d0e7  ldstr    aSelect0FromEnt_5// "select {0} from EntityView x"
0x5d0ec  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d0f1  dup
0x5d0f2  ldstr    aEntity_0// "Entity"
0x5d0f7  ldc.i4.1
0x5d0f8  ldc.i4.0
0x5d0f9  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d0fe  ldstr    aSelect0FromEnt_5// "select {0} from EntityView x"
0x5d103  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d108  dup
0x5d109  ldstr    aEntity_0// "Entity"
0x5d10e  ldc.i4.0
0x5d10f  ldc.i4.1
0x5d110  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d115  ldstr    aSelect0FromEnt_6// "select {0} from EntityAsIfStagedView x"
0x5d11a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d11f  dup
0x5d120  ldstr    aAttribute// "Attribute"
0x5d125  ldc.i4.1
0x5d126  ldc.i4.0
0x5d127  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d12c  ldstr    aSelect0FromAtt_2// "select {0} from AttributeAsIfPublishedV"...
0x5d131  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d136  dup
0x5d137  ldstr    aAttribute// "Attribute"
0x5d13c  ldc.i4.0
0x5d13d  ldc.i4.0
0x5d13e  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d143  ldstr    aSelect0FromAtt_3// "select {0} from AttributeView x join At"...
0x5d148  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d14d  dup
0x5d14e  ldstr    aAttribute// "Attribute"
0x5d153  ldc.i4.0
0x5d154  ldc.i4.1
0x5d155  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d15a  ldstr    aSelect0FromAtt_4// "select {0} from AttributeAsIfStagedView"...
0x5d15f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d164  dup
0x5d165  ldstr    aEntitykey_0// "EntityKey"
0x5d16a  ldc.i4.0
0x5d16b  ldc.i4.0
0x5d16c  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d171  ldstr    aSelect0FromEnt_7// "select {0} from EntityKeyView x"
0x5d176  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d17b  dup
0x5d17c  ldstr    aEntitykey_0// "EntityKey"
0x5d181  ldc.i4.1
0x5d182  ldc.i4.0
0x5d183  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d188  ldstr    aSelect0FromEnt_7// "select {0} from EntityKeyView x"
0x5d18d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d192  dup
0x5d193  ldstr    aEntitykey_0// "EntityKey"
0x5d198  ldc.i4.0
0x5d199  ldc.i4.1
0x5d19a  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d19f  ldstr    aSelect0FromEnt_8// "select {0} from EntityKeyAsIfStagedView"...
0x5d1a4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d1a9  dup
0x5d1aa  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x5d1af  ldc.i4.1
0x5d1b0  ldc.i4.0
0x5d1b1  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d1b6  ldstr    aSelect0FromEnt_9// "select {0} from EntityKeyAttributeView "...
0x5d1bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d1c0  dup
0x5d1c1  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x5d1c6  ldc.i4.0
0x5d1c7  ldc.i4.0
0x5d1c8  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d1cd  ldstr    aSelect0FromEnt_9// "select {0} from EntityKeyAttributeView "...
0x5d1d2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d1d7  dup
0x5d1d8  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x5d1dd  ldc.i4.0
0x5d1de  ldc.i4.1
0x5d1df  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d1e4  ldstr    aSelect0FromEnt_10// "select {0} from EntityKeyAttributeAsIfS"...
0x5d1e9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d1ee  dup
0x5d1ef  ldstr    aAttributelooku// "AttributeLookupValue"
0x5d1f4  ldc.i4.1
0x5d1f5  ldc.i4.0
0x5d1f6  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d1fb  ldstr    aSelect0FromAtt_5// "select {0} from AttributeLookupValueAsI"...
0x5d200  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d205  dup
0x5d206  ldstr    aAttributelooku// "AttributeLookupValue"
0x5d20b  ldc.i4.0
0x5d20c  ldc.i4.0
0x5d20d  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d212  ldstr    aSelect0FromAtt_6// "select {0} from AttributeLookupValueVie"...
0x5d217  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d21c  dup
0x5d21d  ldstr    aAttributelooku// "AttributeLookupValue"
0x5d222  ldc.i4.0
0x5d223  ldc.i4.1
0x5d224  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d229  ldstr    aSelect0FromAtt_7// "select {0} from AttributeLookupValueAsI"...
0x5d22e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d233  dup
0x5d234  ldstr    aAttributepickl// "AttributePicklistValue"
0x5d239  ldc.i4.1
0x5d23a  ldc.i4.0
0x5d23b  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d240  ldstr    aSelect0FromAtt_8// "select {0} from AttributePicklistValueA"...
0x5d245  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d24a  dup
0x5d24b  ldstr    aAttributepickl// "AttributePicklistValue"
0x5d250  ldc.i4.0
0x5d251  ldc.i4.0
0x5d252  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d257  ldstr    aSelect0FromAtt_9// "select {0} from AttributePicklistValueV"...
0x5d25c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d261  dup
0x5d262  ldstr    aAttributepickl// "AttributePicklistValue"
0x5d267  ldc.i4.0
0x5d268  ldc.i4.1
0x5d269  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d26e  ldstr    aSelect0FromAtt_10// "select {0} from AttributePicklistValueA"...
0x5d273  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d278  dup
0x5d279  ldstr    aLocalizedlabel// "LocalizedLabel"
0x5d27e  ldc.i4.1
0x5d27f  ldc.i4.0
0x5d280  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d285  ldstr    aSelect0FromLoc_0// "select {0} from LocalizedLabelAsIfPubli"...
0x5d28a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d28f  dup
0x5d290  ldstr    aLocalizedlabel// "LocalizedLabel"
0x5d295  ldc.i4.0
0x5d296  ldc.i4.0
0x5d297  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d29c  ldstr    aSelect0FromLoc_1// "select {0} from LocalizedLabelView x wh"...
0x5d2a1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d2a6  dup
0x5d2a7  ldstr    aLocalizedlabel// "LocalizedLabel"
0x5d2ac  ldc.i4.0
0x5d2ad  ldc.i4.1
0x5d2ae  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d2b3  ldstr    aSelect0FromLoc_2// "select {0} from LocalizedLabelAsIfStage"...
0x5d2b8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d2bd  dup
0x5d2be  ldstr    aEntityrelation_0// "EntityRelationship"
0x5d2c3  ldc.i4.0
0x5d2c4  ldc.i4.0
0x5d2c5  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d2ca  ldstr    aSelect0FromEnt_11// "select {0} from EntityRelationshipView "...
0x5d2cf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d2d4  dup
0x5d2d5  ldstr    aEntityrelation_0// "EntityRelationship"
0x5d2da  ldc.i4.1
0x5d2db  ldc.i4.0
0x5d2dc  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d2e1  ldstr    aSelect0FromEnt_11// "select {0} from EntityRelationshipView "...
0x5d2e6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d2eb  dup
0x5d2ec  ldstr    aEntityrelation_0// "EntityRelationship"
0x5d2f1  ldc.i4.0
0x5d2f2  ldc.i4.1
0x5d2f3  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d2f8  ldstr    aSelect0FromEnt_12// "select {0} from EntityRelationshipAsIfS"...
0x5d2fd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d302  dup
0x5d303  ldstr    aRelationship_0// "Relationship"
0x5d308  ldc.i4.0
0x5d309  ldc.i4.0
0x5d30a  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d30f  ldstr    aSelect0FromRel_1// "select {0} from RelationshipView x"
0x5d314  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d319  dup
0x5d31a  ldstr    aRelationship_0// "Relationship"
0x5d31f  ldc.i4.1
0x5d320  ldc.i4.0
0x5d321  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d326  ldstr    aSelect0FromRel_1// "select {0} from RelationshipView x"
0x5d32b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d330  dup
0x5d331  ldstr    aRelationship_0// "Relationship"
0x5d336  ldc.i4.0
0x5d337  ldc.i4.1
0x5d338  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d33d  ldstr    aSelect0FromRel_2// "select {0} from RelationshipAsIfStagedV"...
0x5d342  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d347  dup
0x5d348  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x5d34d  ldc.i4.0
0x5d34e  ldc.i4.0
0x5d34f  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d354  ldstr    aSelect0FromRel_3// "select {0} from RelationshipExtraCondit"...
0x5d359  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d35e  dup
0x5d35f  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x5d364  ldc.i4.1
0x5d365  ldc.i4.0
0x5d366  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d36b  ldstr    aSelect0FromRel_3// "select {0} from RelationshipExtraCondit"...
0x5d370  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d375  dup
0x5d376  ldstr    aRelationshipex_0// "RelationshipExtraCondition"
0x5d37b  ldc.i4.0
0x5d37c  ldc.i4.1
0x5d37d  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d382  ldstr    aSelect0FromRel_4// "select {0} from RelationshipExtraCondit"...
0x5d387  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d38c  dup
0x5d38d  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x5d392  ldc.i4.0
0x5d393  ldc.i4.0
0x5d394  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d399  ldstr    aSelect0FromEnt_13// "select {0} from EntityRelationshipRoleV"...
0x5d39e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d3a3  dup
0x5d3a4  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x5d3a9  ldc.i4.1
0x5d3aa  ldc.i4.0
0x5d3ab  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d3b0  ldstr    aSelect0FromEnt_13// "select {0} from EntityRelationshipRoleV"...
0x5d3b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d3ba  dup
0x5d3bb  ldstr    aEntityrelation_4// "EntityRelationshipRole"
0x5d3c0  ldc.i4.0
0x5d3c1  ldc.i4.1
0x5d3c2  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d3c7  ldstr    aSelect0FromEnt_14// "select {0} from EntityRelationshipRoleA"...
0x5d3cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d3d1  dup
0x5d3d2  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x5d3d7  ldc.i4.0
0x5d3d8  ldc.i4.0
0x5d3d9  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d3de  ldstr    aSelect0FromEnt_15// "select {0} from EntityRelationshipRelat"...
0x5d3e3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d3e8  dup
0x5d3e9  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x5d3ee  ldc.i4.1
0x5d3ef  ldc.i4.0
0x5d3f0  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d3f5  ldstr    aSelect0FromEnt_15// "select {0} from EntityRelationshipRelat"...
0x5d3fa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d3ff  dup
0x5d400  ldstr    aEntityrelation_6// "EntityRelationshipRelationships"
0x5d405  ldc.i4.0
0x5d406  ldc.i4.1
0x5d407  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d40c  ldstr    aSelect0FromEnt_16// "select {0} from EntityRelationshipRelat"...
0x5d411  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d416  dup
0x5d417  ldstr    aViewattribute// "ViewAttribute"
0x5d41c  ldc.i4.0
0x5d41d  ldc.i4.0
0x5d41e  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d423  ldstr    aSelect0FromVie_0// "select {0} from ViewAttributeView x"
0x5d428  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d42d  dup
0x5d42e  ldstr    aViewattribute// "ViewAttribute"
0x5d433  ldc.i4.1
0x5d434  ldc.i4.0
0x5d435  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d43a  ldstr    aSelect0FromVie_0// "select {0} from ViewAttributeView x"
0x5d43f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d444  dup
0x5d445  ldstr    aViewattribute// "ViewAttribute"
0x5d44a  ldc.i4.0
0x5d44b  ldc.i4.1
0x5d44c  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
0x5d451  ldstr    aSelect0FromVie_1// "select {0} from ViewAttributeAsIfStaged"...
0x5d456  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class MetadataSqlGeneratorInput, string>::Add(var<u1>, !!T0)
0x5d45b  dup
0x5d45c  ldstr    aManagedpropert_5// "ManagedProperty"
0x5d461  ldc.i4.0
0x5d462  ldc.i4.0
0x5d463  newobj   instance void MetadataSqlGeneratorInput::.ctor(string metadataEntityName, bool retrieveLatest, bool isInStagedContext)
  ... truncated ...
```
