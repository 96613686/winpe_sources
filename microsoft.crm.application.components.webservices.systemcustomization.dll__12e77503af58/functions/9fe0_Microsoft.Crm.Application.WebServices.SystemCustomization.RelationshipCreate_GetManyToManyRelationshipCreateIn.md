# Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetManyToManyRelationshipCreateInfo

- ea: `0x9fe0`
- end: `0xa0b1`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetManyToManyRelationshipCreateInfo`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x9e50`

## callees

- `0x1a0`
- `0x220`
- `0x240`
- `0xa3d0`

## pseudocode

```c

```

## disassembly

```asm
0x9fe0  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::.ctor()
0x9fe5  stloc.0
0x9fe6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9feb  stloc.1
0x9fec  ldloc.1
0x9fed  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9ff2  dup
0x9ff3  ldarg.0
0x9ff4  ldstr    aCurrententityn// "currententityname"
0x9ff9  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x9ffe  ldc.i4.1
0x9fff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xa004  stloc.2
0xa005  ldarg.0
0xa006  ldstr    aOtherentitynam// "otherentityname"
0xa00b  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa010  ldc.i4.1
0xa011  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xa016  stloc.3
0xa017  ldloc.0
0xa018  ldarg.0
0xa019  ldstr    aSchemaname// "schemaname"
0xa01e  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa023  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::set_SchemaName(string)
0xa028  ldloc.0
0xa029  ldarg.0
0xa02a  ldstr    aIntersectentit// "intersectentityname"
0xa02f  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa034  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::set_IntersectEntitySchemaName(string)
0xa039  ldloc.0
0xa03a  ldloc.2
0xa03b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xa040  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::set_EntityOneId(valuetype [mscorlib]System.Guid)
0xa045  ldloc.0
0xa046  ldloc.3
0xa047  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xa04c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipCreateInfo::set_EntityTwoId(valuetype [mscorlib]System.Guid)
0xa051  ldloc.0
0xa052  ldloc.1
0xa053  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa058  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::set_EntityOneRoleInfo(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo)
0xa05d  ldarg.0
0xa05e  ldstr    aAssociatedmenu// "associatedmenu"
0xa063  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0xa068  ldloc.0
0xa069  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::get_EntityOneRoleInfo()
0xa06e  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetAssociatedMenuInfo(class Microsoft.Crm.Application.WebServices.ParameterBag menuBag, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo roleInfo)
0xa073  ldloc.0
0xa074  ldloc.1
0xa075  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa07a  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::set_EntityTwoRoleInfo(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo)
0xa07f  ldarg.0
0xa080  ldstr    aAssociatedmenu_0// "associatedmenuotherentity"
0xa085  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0xa08a  ldloc.0
0xa08b  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::get_EntityTwoRoleInfo()
0xa090  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetAssociatedMenuInfo(class Microsoft.Crm.Application.WebServices.ParameterBag menuBag, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo roleInfo)
0xa095  ldloc.0
0xa096  ldarg.0
0xa097  ldstr    aIsvalidforadva// "isvalidforadvancedfind"
0xa09c  ldc.i4.1
0xa09d  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name, int32 defaultValue)
0xa0a2  ldc.i4.0
0xa0a3  cgt.un
0xa0a5  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0xa0aa  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.ManyToManyRelationshipInfo::set_IsValidForAdvancedFind(valuetype [mscorlib]System.Nullable`1<bool>)
0xa0af  ldloc.0
0xa0b0  ret
```
