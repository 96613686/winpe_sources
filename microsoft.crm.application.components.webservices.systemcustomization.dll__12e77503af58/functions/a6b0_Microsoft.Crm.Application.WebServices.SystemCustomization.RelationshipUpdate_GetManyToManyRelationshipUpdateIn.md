# Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetManyToManyRelationshipUpdateInfo

- ea: `0xa6b0`
- end: `0xa7ea`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetManyToManyRelationshipUpdateInfo`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xa600`

## callees

- `0x1a0`
- `0x220`
- `0x270`
- `0x330`
- `0xa6b0`
- `0xaa00`

## pseudocode

```c

```

## disassembly

```asm
0xa6b0  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipUpdateInfo::.ctor()
0xa6b5  stloc.0
0xa6b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa6bb  stloc.1
0xa6bc  ldloc.0
0xa6bd  ldloc.1
0xa6be  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa6c3  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::set_EntityOneRoleInfo(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo)
0xa6c8  ldloc.0
0xa6c9  ldloc.1
0xa6ca  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa6cf  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::set_EntityTwoRoleInfo(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo)
0xa6d4  ldarg.1
0xa6d5  ldarg.0
0xa6d6  ldstr    aEntityrelation// "entityrelationshipid"
0xa6db  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0xa6e0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntityRelationship(valuetype [mscorlib]System.Guid)
0xa6e5  ldarg.1
0xa6e6  ldarg.0
0xa6e7  ldstr    aCurrententityn// "currententityname"
0xa6ec  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa6f1  ldc.i4.1
0xa6f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xa6f7  stloc.2
0xa6f8  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship
0xa6fd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityRelationshipRoleCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManyToManyEntityRelationship::get_AssociationEntityRelationshipRoles()
0xa702  dup
0xa703  ldc.i4.0
0xa704  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Item(!!T0)
0xa709  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AssociationEntityRelationshipRole
0xa70e  stloc.3
0xa70f  ldc.i4.1
0xa710  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole>::get_Item(!!T0)
0xa715  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AssociationEntityRelationshipRole
0xa71a  stloc.s  4
0xa71c  ldloc.3
0xa71d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AssociationEntityRelationshipRole::get_AssociationRoleOrdinal()
0xa722  ldc.i4.1
0xa723  beq.s    loc_A72B
0xa725  ldloc.3
0xa726  ldloc.s  4
0xa728  stloc.3
0xa729  stloc.s  4
0xa72b  ldloc.0
0xa72c  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::get_EntityOneRoleInfo()
0xa731  ldloc.3
0xa732  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityRelationshipRoleId()
0xa737  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::set_EntityRelationshipRoleId(valuetype [mscorlib]System.Guid)
0xa73c  ldloc.0
0xa73d  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::get_EntityTwoRoleInfo()
0xa742  ldloc.s  4
0xa744  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityRelationshipRoleId()
0xa749  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::set_EntityRelationshipRoleId(valuetype [mscorlib]System.Guid)
0xa74e  ldloc.3
0xa74f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityId()
0xa754  ldloc.s  4
0xa756  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityId()
0xa75b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa760  brtrue.s loc_A775
0xa762  ldloc.3
0xa763  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipRole::get_EntityId()
0xa768  ldloc.2
0xa769  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xa76e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xa773  brfalse.s loc_A7A3
0xa775  ldarg.0
0xa776  ldstr    aAssociatedmenu// "associatedmenu"
0xa77b  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0xa780  ldloc.0
0xa781  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::get_EntityOneRoleInfo()
0xa786  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetAssociatedMenuInfo(class Microsoft.Crm.Application.WebServices.ParameterBag menuBag, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo roleInfo)
0xa78b  ldarg.0
0xa78c  ldstr    aAssociatedmenu_0// "associatedmenuotherentity"
0xa791  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0xa796  ldloc.0
0xa797  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::get_EntityTwoRoleInfo()
0xa79c  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetAssociatedMenuInfo(class Microsoft.Crm.Application.WebServices.ParameterBag menuBag, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo roleInfo)
0xa7a1  br.s     loc_A7CF
0xa7a3  ldarg.0
0xa7a4  ldstr    aAssociatedmenu// "associatedmenu"
0xa7a9  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0xa7ae  ldloc.0
0xa7af  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::get_EntityTwoRoleInfo()
0xa7b4  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetAssociatedMenuInfo(class Microsoft.Crm.Application.WebServices.ParameterBag menuBag, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo roleInfo)
0xa7b9  ldarg.0
0xa7ba  ldstr    aAssociatedmenu_0// "associatedmenuotherentity"
0xa7bf  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0xa7c4  ldloc.0
0xa7c5  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::get_EntityOneRoleInfo()
0xa7ca  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetAssociatedMenuInfo(class Microsoft.Crm.Application.WebServices.ParameterBag menuBag, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo roleInfo)
0xa7cf  ldloc.0
0xa7d0  ldarg.0
0xa7d1  ldstr    aIsvalidforadva// "isvalidforadvancedfind"
0xa7d6  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0xa7db  ldc.i4.0
0xa7dc  cgt.un
0xa7de  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0xa7e3  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::set_IsValidForAdvancedFind(valuetype [mscorlib]System.Nullable`1<bool>)
0xa7e8  ldloc.0
0xa7e9  ret
```
