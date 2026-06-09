# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdateIcons

- ea: `0x37d0`
- end: `0x387d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdateIcons`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xb080`

## callees

- `0x1a0`
- `0x330`
- `0x37d0`
- `0x4020`
- `0x4120`

## string_xrefs

- `0x386d`: `System entity icons cannot be updated.`

## pseudocode

```c

```

## disassembly

```asm
0x37d0  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::CheckPrivileges()
0x37d5  ldarg.1
0x37d6  ldstr    aEntityid// "entityid"
0x37db  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x37e0  stloc.0
0x37e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x37e6  stloc.1
0x37e7  ldloc.1
0x37e8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x37ed  ldloc.0
0x37ee  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x37f3  stloc.2
0x37f4  ldloc.2
0x37f5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0x37fa  brfalse.s loc_386D
0x37fc  ldloc.0
0x37fd  ldloc.1
0x37fe  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::.ctor(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3803  stloc.3
0x3804  ldloc.3
0x3805  ldarg.1
0x3806  ldstr    aIcons// "icons"
0x380b  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x3810  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetIconParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3815  ldloc.3
0x3816  ldloc.2
0x3817  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_DataProviderId()
0x381c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_DataProviderId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x3821  ldloc.3
0x3822  ldloc.2
0x3823  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_DataSourceId()
0x3828  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_DataSourceId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x382d  ldloc.3
0x382e  ldloc.2
0x382f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ExternalName()
0x3834  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_ExternalName(string)
0x3839  ldloc.2
0x383a  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityService [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityServiceFactory::CreateEntityService(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0x383f  ldloc.0
0x3840  ldloc.3
0x3841  ldc.i4.1
0x3842  ldarg.0
0x3843  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3848  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x384d  brtrue.s loc_3852
0x384f  ldarg.0
0x3850  br.s     loc_3857
0x3852  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x3857  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityService::Update(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo, bool, valuetype [mscorlib]System.Guid)
0x385c  ldloc.2
0x385d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x3862  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3867  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x386c  ret
0x386d  ldstr    aSystemEntityIc// "System entity icons cannot be updated."
0x3872  ldc.i4   0x8004F653
0x3877  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x387c  throw
```
