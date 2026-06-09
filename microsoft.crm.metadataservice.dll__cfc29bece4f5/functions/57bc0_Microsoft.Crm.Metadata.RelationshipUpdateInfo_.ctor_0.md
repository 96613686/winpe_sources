# Microsoft.Crm.Metadata.RelationshipUpdateInfo::.ctor_0

- ea: `0x57bc0`
- end: `0x57e07`
- name: `Microsoft.Crm.Metadata.RelationshipUpdateInfo::.ctor_0`
- size: `583`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x37ad0`
- `0x4f060`
- `0x554c0`

## callees

- `0x2ecd0`
- `0x48cb0`
- `0x496e0`
- `0x49700`
- `0x49720`
- `0x57bc0`
- `0x57f60`
- `0x57f80`
- `0x57fc0`
- `0x57fe0`
- `0x58060`
- `0x58120`
- `0x58140`
- `0x58160`
- `0x58360`

## string_xrefs

- `0x57d37`: `cascadedelete`
- `0x57c50`: `The EntityRelationshipDescription of the OneToManyRelationshipUpdateData must contain the entity relationship id`

## pseudocode

```c

```

## disassembly

```asm
0x57bc0  ldarg.0
0x57bc1  ldstr    aDisplaynames// "displaynames"
0x57bc6  ldstr    aDisplayname_0// "displayname"
0x57bcb  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor(string, string)
0x57bd0  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.RelationshipUpdateInfo::<PrimaryEntityInstanceName>k__BackingField
0x57bd5  ldarg.0
0x57bd6  ldstr    aDescriptions// "Descriptions"
0x57bdb  ldstr    aDescription// "Description"
0x57be0  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor(string, string)
0x57be5  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.RelationshipUpdateInfo::<Description>k__BackingField
0x57bea  ldarg.0
0x57beb  ldc.i4.1
0x57bec  stfld    bool Microsoft.Crm.Metadata.RelationshipUpdateInfo::<RelationshipValidForAdvancedFind>k__BackingField
0x57bf1  ldarg.0
0x57bf2  ldc.i4.1
0x57bf3  stfld    bool Microsoft.Crm.Metadata.RelationshipUpdateInfo::<RelationshipAttributeIsCustomizable>k__BackingField
0x57bf8  ldarg.0
0x57bf9  ldc.i4.1
0x57bfa  stfld    bool Microsoft.Crm.Metadata.RelationshipUpdateInfo::<RelationshipAttributeIsRenameable>k__BackingField
0x57bff  ldarg.0
0x57c00  ldc.i4.1
0x57c01  stfld    bool Microsoft.Crm.Metadata.RelationshipUpdateInfo::<RelationshipAttributeCanModifySearchSettings>k__BackingField
0x57c06  ldarg.0
0x57c07  ldc.i4.1
0x57c08  stfld    bool Microsoft.Crm.Metadata.RelationshipUpdateInfo::<RelationshipAttributeCanModifyRequirementLevelSettings>k__BackingField
0x57c0d  ldarg.0
0x57c0e  call     instance void [mscorlib]System.Object::.ctor()
0x57c13  ldarg.0
0x57c14  ldc.i4.0
0x57c15  call     instance void Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_UpdateAttribute(bool value)
0x57c1a  ldarg.0
0x57c1b  ldnull
0x57c1c  call     instance void Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_PrimaryEntityInstanceName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection value)
0x57c21  ldarg.0
0x57c22  ldnull
0x57c23  call     instance void Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_Description(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection value)
0x57c28  ldarg.0
0x57c29  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x57c2e  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipUpdateInfo::primaryEntityId
0x57c33  ldarg.0
0x57c34  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x57c39  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipUpdateInfo::relatedEntityId
0x57c3e  ldarg.1
0x57c3f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x57c44  ldstr    aEntityrelation// "entityrelationshipid"
0x57c49  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x57c4e  brfalse.s loc_57C5B
0x57c50  ldstr    aTheEntityrelat_0// "The EntityRelationshipDescription of th"...
0x57c55  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x57c5a  throw
0x57c5b  ldarg.0
0x57c5c  ldarg.1
0x57c5d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x57c62  ldstr    aEntityrelation// "entityrelationshipid"
0x57c67  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57c6c  unbox.any [mscorlib]System.Guid
0x57c71  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipUpdateInfo::entityRelationshipId
0x57c76  ldarg.1
0x57c77  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x57c7c  ldstr    aIscustomizable// "iscustomizable"
0x57c81  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x57c86  brtrue.s loc_57CAF
0x57c88  ldarg.0
0x57c89  ldarg.1
0x57c8a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x57c8f  ldstr    aIscustomizable// "iscustomizable"
0x57c94  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57c99  unbox.any [mscorlib]System.Boolean
0x57c9e  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x57ca3  call     instance void Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_IsCustomizable(valuetype [mscorlib]System.Nullable`1<bool> value)
0x57ca8  ldarg.0
0x57ca9  ldc.i4.1
0x57caa  stfld    bool Microsoft.Crm.Metadata.RelationshipUpdateInfo::_updateEntityRelationship
0x57caf  ldarg.1
0x57cb0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x57cb5  ldstr    aIshierarchical// "ishierarchical"
0x57cba  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x57cbf  brtrue.s loc_57CE8
0x57cc1  ldarg.0
0x57cc2  ldarg.1
0x57cc3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x57cc8  ldstr    aIshierarchical// "ishierarchical"
0x57ccd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57cd2  unbox.any [mscorlib]System.Boolean
0x57cd7  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x57cdc  call     instance void Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_IsHierarchical(valuetype [mscorlib]System.Nullable`1<bool> value)
0x57ce1  ldarg.0
0x57ce2  ldc.i4.1
0x57ce3  stfld    bool Microsoft.Crm.Metadata.RelationshipUpdateInfo::_updateEntityRelationship
0x57ce8  ldarg.1
0x57ce9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x57cee  ldstr    aCanchangehiera// "canchangehierarchicalsettings"
0x57cf3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x57cf8  brtrue.s loc_57D21
0x57cfa  ldarg.0
0x57cfb  ldarg.1
0x57cfc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.EntityRelationshipData::get_EntityRelationshipDescription()
0x57d01  ldstr    aCanchangehiera// "canchangehierarchicalsettings"
0x57d06  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57d0b  unbox.any [mscorlib]System.Boolean
0x57d10  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x57d15  call     instance void Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CanChangeHierarchicalSettings(valuetype [mscorlib]System.Nullable`1<bool> value)
0x57d1a  ldarg.0
0x57d1b  ldc.i4.1
0x57d1c  stfld    bool Microsoft.Crm.Metadata.RelationshipUpdateInfo::_updateEntityRelationship
0x57d21  ldarg.1
0x57d22  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.OneToManyRelationshipUpdateData::get_RelationshipDescription()
0x57d27  stloc.0
0x57d28  ldloc.0
0x57d29  brfalse  loc_57DCD
0x57d2e  ldarg.0
0x57d2f  ldc.i4.1
0x57d30  stfld    bool Microsoft.Crm.Metadata.RelationshipUpdateInfo::<UpdateRelationship>k__BackingField
0x57d35  ldarg.0
0x57d36  ldloc.0
0x57d37  ldstr    aCascadedelete// "cascadedelete"
0x57d3c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57d41  stfld    object Microsoft.Crm.Metadata.RelationshipUpdateInfo::cascadeDelete
0x57d46  ldarg.0
0x57d47  ldloc.0
0x57d48  ldstr    aCascadeassign// "cascadeassign"
0x57d4d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57d52  stfld    object Microsoft.Crm.Metadata.RelationshipUpdateInfo::cascadeAssign
0x57d57  ldarg.0
0x57d58  ldloc.0
0x57d59  ldstr    aCascadeshare// "cascadeshare"
0x57d5e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57d63  stfld    object Microsoft.Crm.Metadata.RelationshipUpdateInfo::cascadeShare
0x57d68  ldarg.0
0x57d69  ldloc.0
0x57d6a  ldstr    aCascadeunshare// "cascadeunshare"
0x57d6f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57d74  stfld    object Microsoft.Crm.Metadata.RelationshipUpdateInfo::cascadeUnshare
0x57d79  ldarg.0
0x57d7a  ldloc.0
0x57d7b  ldstr    aCascadereparen// "cascadereparent"
0x57d80  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57d85  stfld    object Microsoft.Crm.Metadata.RelationshipUpdateInfo::cascadeReparent
0x57d8a  ldloc.0
0x57d8b  ldstr    aCascaderollupv// "cascaderollupview"
0x57d90  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNullOrNameInvalid(string)
0x57d95  brtrue.s loc_57DA8
0x57d97  ldarg.0
0x57d98  ldloc.0
0x57d99  ldstr    aCascaderollupv// "cascaderollupview"
0x57d9e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57da3  stfld    object Microsoft.Crm.Metadata.RelationshipUpdateInfo::cascadeRollupView
0x57da8  ldloc.0
0x57da9  ldstr    aIsvalidforadva// "isvalidforadvancedfind"
0x57dae  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x57db3  brtrue.s loc_57DD4
0x57db5  ldarg.0
0x57db6  ldloc.0
0x57db7  ldstr    aIsvalidforadva// "isvalidforadvancedfind"
0x57dbc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x57dc1  unbox.any [mscorlib]System.Boolean
0x57dc6  call     instance void Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_RelationshipValidForAdvancedFind(bool value)
0x57dcb  br.s     loc_57DD4
0x57dcd  ldarg.0
0x57dce  ldc.i4.0
0x57dcf  stfld    bool Microsoft.Crm.Metadata.RelationshipUpdateInfo::<UpdateRelationship>k__BackingField
0x57dd4  ldarg.1
0x57dd5  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.OneToManyRelationshipUpdateData::get_ReferencingEntityRelationshipRole()
0x57dda  brfalse.s loc_57DED
0x57ddc  ldarg.0
0x57ddd  ldarg.1
0x57dde  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.OneToManyRelationshipUpdateData::get_ReferencingEntityRelationshipRole()
0x57de3  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::.ctor(class Microsoft.Crm.Metadata.EntityRelationshipRoleData roleData)
0x57de8  call     instance void Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_ReferencingEntityRoleInfo(class Microsoft.Crm.Metadata.EntityRelationshipRoleInfo value)
0x57ded  ldarg.1
0x57dee  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.OneToManyRelationshipUpdateData::get_ReferencedEntityRelationshipRole()
0x57df3  brfalse.s loc_57E06
0x57df5  ldarg.0
0x57df6  ldarg.1
0x57df7  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleData Microsoft.Crm.Metadata.OneToManyRelationshipUpdateData::get_ReferencedEntityRelationshipRole()
0x57dfc  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::.ctor(class Microsoft.Crm.Metadata.EntityRelationshipRoleData roleData)
0x57e01  call     instance void Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_ReferencedEntityRoleInfo(class Microsoft.Crm.Metadata.EntityRelationshipRoleInfo value)
0x57e06  ret
```
