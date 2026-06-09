# Microsoft.Crm.Metadata.RelationshipCreateInfo::.ctor_0

- ea: `0x4c930`
- end: `0x4cddf`
- name: `Microsoft.Crm.Metadata.RelationshipCreateInfo::.ctor_0`
- size: `1199`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `broker_com_uri`

## callers

- `0x4eff0`

## callees

- `0x2bda0`
- `0x2ecd0`
- `0x48b90`
- `0x48bf0`
- `0x48c30`
- `0x48cb0`
- `0x49470`
- `0x49480`
- `0x49490`
- `0x494a0`
- `0x494c0`
- `0x494e0`
- `0x499f0`
- `0x4c930`
- `0x4ced0`
- `0x4cef0`
- `0x4cf10`
- `0x4cf50`
- `0x4cfb0`
- `0x4d090`
- `0x4d0b0`
- `0x4d0d0`
- `0x4d110`
- `0x4d130`
- `0x4d150`
- `0x4d170`
- `0x4d180`
- `0x4d190`
- `0x4d1f0`
- `0x4d210`
- `0x4d230`
- `0x4d250`
- `0x4d2b0`
- `0x4d350`
- `0x4d8b0`
- `0x4d8d0`

## string_xrefs

- `0x4c9a7`: `cascadedelete`
- `0x4cc32`: `The Referenced EntityRelationshipRole of the OneToManyRelationshipCreateData must contain the entity id`
- `0x4cc54`: `The Referencing EntityRelationshipRole of the OneToManyRelationshipCreateData must contain the entity id`

## pseudocode

```c

```

## disassembly

```asm
0x4c930  ldarg.0
0x4c931  ldc.i4.1
0x4c932  stfld    bool Microsoft.Crm.Metadata.RelationshipCreateInfo::<RelationshipValidForAdvancedFind>k__BackingField
0x4c937  ldarg.0
0x4c938  ldc.i4.1
0x4c939  stfld    bool Microsoft.Crm.Metadata.RelationshipCreateInfo::<RelationshipAttributeIsCustomizable>k__BackingField
0x4c93e  ldarg.0
0x4c93f  ldc.i4.1
0x4c940  stfld    bool Microsoft.Crm.Metadata.RelationshipCreateInfo::<RelationshipAttributeIsCustomField>k__BackingField
0x4c945  ldarg.0
0x4c946  ldc.i4.1
0x4c947  stfld    bool Microsoft.Crm.Metadata.RelationshipCreateInfo::<RelationshipAttributeIsRenameable>k__BackingField
0x4c94c  ldarg.0
0x4c94d  ldc.i4.1
0x4c94e  stfld    bool Microsoft.Crm.Metadata.RelationshipCreateInfo::<RelationshipAttributeCanModifySearchSettings>k__BackingField
0x4c953  ldarg.0
0x4c954  ldc.i4.1
0x4c955  stfld    bool Microsoft.Crm.Metadata.RelationshipCreateInfo::<RelationshipAttributeCanModifyRequirementLevelSettings>k__BackingField
0x4c95a  ldarg.0
0x4c95b  ldstr    aDisplaynames// "displaynames"
0x4c960  ldstr    aDisplayname_0// "displayname"
0x4c965  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor(string, string)
0x4c96a  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.RelationshipCreateInfo::<PrimaryEntityInstanceName>k__BackingField
0x4c96f  ldarg.0
0x4c970  ldstr    aDescriptions// "Descriptions"
0x4c975  ldstr    aDescription// "Description"
0x4c97a  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor(string, string)
0x4c97f  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.RelationshipCreateInfo::<Description>k__BackingField
0x4c984  ldarg.0
0x4c985  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4c98a  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipCreateInfo::primaryEntityId
0x4c98f  ldarg.0
0x4c990  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4c995  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipCreateInfo::relatedEntityId
0x4c99a  ldarg.0
0x4c99b  call     instance void [mscorlib]System.Object::.ctor()
0x4c9a0  ldarg.0
0x4c9a1  ldarg.1
0x4c9a2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_RelationshipDescription()
0x4c9a7  ldstr    aCascadedelete// "cascadedelete"
0x4c9ac  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4c9b1  stfld    object Microsoft.Crm.Metadata.RelationshipCreateInfo::cascadeDelete
0x4c9b6  ldarg.0
0x4c9b7  ldarg.1
0x4c9b8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_RelationshipDescription()
0x4c9bd  ldstr    aCascadeassign// "cascadeassign"
0x4c9c2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4c9c7  stfld    object Microsoft.Crm.Metadata.RelationshipCreateInfo::cascadeAssign
0x4c9cc  ldarg.0
0x4c9cd  ldarg.1
0x4c9ce  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_RelationshipDescription()
0x4c9d3  ldstr    aCascadeshare// "cascadeshare"
0x4c9d8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4c9dd  stfld    object Microsoft.Crm.Metadata.RelationshipCreateInfo::cascadeShare
0x4c9e2  ldarg.0
0x4c9e3  ldarg.1
0x4c9e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_RelationshipDescription()
0x4c9e9  ldstr    aCascadeunshare// "cascadeunshare"
0x4c9ee  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4c9f3  stfld    object Microsoft.Crm.Metadata.RelationshipCreateInfo::cascadeUnshare
0x4c9f8  ldarg.0
0x4c9f9  ldarg.1
0x4c9fa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_RelationshipDescription()
0x4c9ff  ldstr    aCascademerge// "cascademerge"
0x4ca04  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4ca09  stfld    object Microsoft.Crm.Metadata.RelationshipCreateInfo::cascadeMerge
0x4ca0e  ldarg.0
0x4ca0f  ldarg.1
0x4ca10  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_RelationshipDescription()
0x4ca15  ldstr    aCascadereparen// "cascadereparent"
0x4ca1a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4ca1f  stfld    object Microsoft.Crm.Metadata.RelationshipCreateInfo::cascadeReparent
0x4ca24  ldarg.0
0x4ca25  ldc.i4.1
0x4ca26  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_ShouldGenerateViewAttribute(bool value)
0x4ca2b  ldarg.1
0x4ca2c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_RelationshipDescription()
0x4ca31  ldstr    aCascaderollupv// "cascaderollupview"
0x4ca36  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x4ca3b  brtrue.s loc_4CA53
0x4ca3d  ldarg.0
0x4ca3e  ldarg.1
0x4ca3f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_RelationshipDescription()
0x4ca44  ldstr    aCascaderollupv// "cascaderollupview"
0x4ca49  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4ca4e  stfld    object Microsoft.Crm.Metadata.RelationshipCreateInfo::cascadeRollupView
0x4ca53  ldarg.1
0x4ca54  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x4ca59  ldstr    aSchemaname// "schemaname"
0x4ca5e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4ca63  brtrue.s loc_4CA80
0x4ca65  ldarg.0
0x4ca66  ldarg.1
0x4ca67  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x4ca6c  ldstr    aSchemaname// "schemaname"
0x4ca71  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4ca76  castclass [mscorlib]System.String
0x4ca7b  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_SchemaName(string value)
0x4ca80  ldarg.0
0x4ca81  ldarg.1
0x4ca82  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x4ca87  ldstr    aIscustomizable// "iscustomizable"
0x4ca8c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4ca91  brtrue.s loc_4CAAA
0x4ca93  ldarg.1
0x4ca94  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x4ca99  ldstr    aIscustomizable// "iscustomizable"
0x4ca9e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4caa3  unbox.any [mscorlib]System.Boolean
0x4caa8  br.s     loc_4CAAB
0x4caaa  ldc.i4.1
0x4caab  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_IsCustomizable(bool value)
0x4cab0  ldarg.0
0x4cab1  ldarg.1
0x4cab2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x4cab7  ldstr    aIshierarchical// "ishierarchical"
0x4cabc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x4cac1  brtrue.s loc_4CADA
0x4cac3  ldarg.1
0x4cac4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x4cac9  ldstr    aIshierarchical// "ishierarchical"
0x4cace  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4cad3  unbox.any [mscorlib]System.Boolean
0x4cad8  br.s     loc_4CADB
0x4cada  ldc.i4.0
0x4cadb  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_IsHierarchical(bool value)
0x4cae0  ldarg.0
0x4cae1  ldarg.1
0x4cae2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x4cae7  ldstr    aCanchangehiera// "canchangehierarchicalsettings"
0x4caec  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x4caf1  brtrue.s loc_4CB0A
0x4caf3  ldarg.1
0x4caf4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x4caf9  ldstr    aCanchangehiera// "canchangehierarchicalsettings"
0x4cafe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4cb03  unbox.any [mscorlib]System.Boolean
0x4cb08  br.s     loc_4CB0B
0x4cb0a  ldc.i4.0
0x4cb0b  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CanChangeHierarchicalSettings(bool value)
0x4cb10  ldarg.1
0x4cb11  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_RelationshipDescription()
0x4cb16  ldstr    aIsvalidforadva// "isvalidforadvancedfind"
0x4cb1b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4cb20  brtrue.s loc_4CB3D
0x4cb22  ldarg.0
0x4cb23  ldarg.1
0x4cb24  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_RelationshipDescription()
0x4cb29  ldstr    aIsvalidforadva// "isvalidforadvancedfind"
0x4cb2e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4cb33  unbox.any [mscorlib]System.Boolean
0x4cb38  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipValidForAdvancedFind(bool value)
0x4cb3d  ldarg.1
0x4cb3e  callvirt instance class Microsoft.Crm.Metadata.LookupAttributeCreateData Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_ReferencingAttribute()
0x4cb43  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x4cb48  stloc.0
0x4cb49  ldloc.0
0x4cb4a  ldstr    aAttributerequi// "attributerequiredlevelid"
0x4cb4f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4cb54  brtrue.s loc_4CB6C
0x4cb56  ldarg.0
0x4cb57  ldloc.0
0x4cb58  ldstr    aAttributerequi// "attributerequiredlevelid"
0x4cb5d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4cb62  unbox.any [mscorlib]System.Int32
0x4cb67  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeRequiredLevel(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel value)
0x4cb6c  ldloc.0
0x4cb6d  ldstr    aName// "name"
0x4cb72  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4cb77  brtrue.s loc_4CB8F
0x4cb79  ldarg.0
0x4cb7a  ldloc.0
0x4cb7b  ldstr    aName// "name"
0x4cb80  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4cb85  castclass [mscorlib]System.String
0x4cb8a  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeName(string value)
0x4cb8f  ldloc.0
0x4cb90  ldstr    aIntroducedvers// "introducedversion"
0x4cb95  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4cb9a  brtrue.s loc_4CBB7
0x4cb9c  ldarg.0
0x4cb9d  ldloc.0
0x4cb9e  ldstr    aIntroducedvers// "introducedversion"
0x4cba3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4cba8  castclass [mscorlib]System.String
0x4cbad  call     class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::ToVersionFromString(string)
0x4cbb2  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_IntroducedVersion(class [mscorlib]System.Version value)
0x4cbb7  ldarg.0
0x4cbb8  ldarg.1
0x4cbb9  callvirt instance bool Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_IsPartOfPolymorphicRelationships()
0x4cbbe  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_IsPartOfPolymorphicRelationships(bool value)
0x4cbc3  ldarg.0
0x4cbc4  call     instance bool Microsoft.Crm.Metadata.RelationshipCreateInfo::get_IsPartOfPolymorphicRelationships()
0x4cbc9  brfalse.s loc_4CBE6
0x4cbcb  ldarg.0
0x4cbcc  ldloc.0
0x4cbcd  ldstr    aAttributetypei// "attributetypeid"
0x4cbd2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4cbd7  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo
0x4cbdc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x4cbe1  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeTypeName(string value)
0x4cbe6  ldarg.0
0x4cbe7  ldarg.0
0x4cbe8  call     instance bool Microsoft.Crm.Metadata.RelationshipCreateInfo::get_IsPartOfPolymorphicRelationships()
0x4cbed  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_IsLogical(bool value)
0x4cbf2  ldarg.0
0x4cbf3  ldc.i4.1
0x4cbf4  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipBehaviour(int32 value)
0x4cbf9  ldarg.0
0x4cbfa  ldarg.1
0x4cbfb  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_ReferencingEntityRelationshipRole()
0x4cc00  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::.ctor(class Microsoft.Crm.Metadata.EntityRelationshipRoleData roleData)
0x4cc05  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_ReferencingEntityRoleInfo(class Microsoft.Crm.Metadata.EntityRelationshipRoleInfo value)
0x4cc0a  ldarg.0
0x4cc0b  ldarg.1
0x4cc0c  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_ReferencedEntityRelationshipRole()
0x4cc11  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::.ctor(class Microsoft.Crm.Metadata.EntityRelationshipRoleData roleData)
0x4cc16  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_ReferencedEntityRoleInfo(class Microsoft.Crm.Metadata.EntityRelationshipRoleInfo value)
0x4cc1b  ldarg.1
0x4cc1c  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_ReferencedEntityRelationshipRole()
0x4cc21  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipRoleData::get_EntityRelationshipRoleDescription()
0x4cc26  ldstr    aEntityid// "entityid"
0x4cc2b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4cc30  brfalse.s loc_4CC3D
0x4cc32  ldstr    aTheReferencedE// "The Referenced EntityRelationshipRole o"...
0x4cc37  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x4cc3c  throw
0x4cc3d  ldarg.1
0x4cc3e  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_ReferencingEntityRelationshipRole()
0x4cc43  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipRoleData::get_EntityRelationshipRoleDescription()
0x4cc48  ldstr    aEntityid// "entityid"
0x4cc4d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4cc52  brfalse.s loc_4CC5F
0x4cc54  ldstr    aTheReferencing// "The Referencing EntityRelationshipRole "...
0x4cc59  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x4cc5e  throw
0x4cc5f  ldarg.2
0x4cc60  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.MetadataCacheUtil::IsStagedMetadataCacheAndPartialLoadMetadataCacheEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4cc65  brfalse.s loc_4CCCC
0x4cc67  ldarg.0
0x4cc68  ldarg.2
0x4cc69  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4cc6e  ldarg.1
0x4cc6f  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_ReferencedEntityRelationshipRole()
0x4cc74  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipRoleData::get_EntityRelationshipRoleDescription()
0x4cc79  ldstr    aEntityid// "entityid"
0x4cc7e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4cc83  unbox.any [mscorlib]System.Guid
0x4cc88  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x4cc8d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x4cc92  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_PrimaryEntityName(string value)
0x4cc97  ldarg.0
0x4cc98  ldarg.2
0x4cc99  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4cc9e  ldarg.1
0x4cc9f  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_ReferencingEntityRelationshipRole()
0x4cca4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipRoleData::get_EntityRelationshipRoleDescription()
0x4cca9  ldstr    aEntityid// "entityid"
0x4ccae  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4ccb3  unbox.any [mscorlib]System.Guid
0x4ccb8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x4ccbd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x4ccc2  call     instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelatedEntityName(string value)
0x4ccc7  br       loc_4CD6F
0x4cccc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::.ctor()
0x4ccd1  ldstr    aEntity_0// "Entity"
0x4ccd6  ldarg.2
0x4ccd7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4ccdc  stloc.1
0x4ccdd  ldloc.1
0x4ccde  ldstr    aName// "name"
0x4cce3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x4cce8  dup
0x4cce9  ldarg.1
0x4ccea  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_ReferencedEntityRelationshipRole()
0x4ccef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipRoleData::get_EntityRelationshipRoleDescription()
0x4ccf4  ldstr    aEntityid// "entityid"
0x4ccf9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4ccfe  unbox.any [mscorlib]System.Guid
0x4cd03  ldstr    aEntity_0// "Entity"
0x4cd08  ldarg.2
0x4cd09  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4cd0e  ldloc.1
0x4cd0f  ldarg.2
0x4cd10  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x4cd15  stloc.2
0x4cd16  ldarg.1
0x4cd17  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.OneToManyRelationshipCreateData::get_ReferencingEntityRelationshipRole()
0x4cd1c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipRoleData::get_EntityRelationshipRoleDescription()
0x4cd21  ldstr    aEntityid// "entityid"
0x4cd26  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4cd2b  unbox.any [mscorlib]System.Guid
0x4cd30  ldstr    aEntity_0// "Entity"
0x4cd35  ldarg.2
0x4cd36  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4cd3b  ldloc.1
0x4cd3c  ldarg.2
0x4cd3d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x4cd42  stloc.3
0x4cd43  ldarg.0
  ... truncated ...
```
