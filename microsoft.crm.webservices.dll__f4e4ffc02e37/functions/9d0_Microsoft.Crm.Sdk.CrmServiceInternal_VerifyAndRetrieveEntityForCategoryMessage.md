# Microsoft.Crm.Sdk.CrmServiceInternal::VerifyAndRetrieveEntityForCategoryMessage

- ea: `0x9d0`
- end: `0xa36`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::VerifyAndRetrieveEntityForCategoryMessage`
- size: `102`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x680`
- `0x700`
- `0x760`
- `0x7d0`
- `0x880`

## callees

- `0x9d0`
- `0xaa0`
- `0xb40`
- `0x4ac0`
- `0x4b10`
- `0x4b80`

## pseudocode

```c

```

## disassembly

```asm
0x9d0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0x9d5  stloc.0
0x9d6  ldarg.1
0x9d7  ldstr    aRequest// "Request"
0x9dc  call     string [mscorlib]System.String::Concat(string, string)
0x9e1  ldarg.3
0x9e2  ldloc.0
0x9e3  call     class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBuilderFactory::Create(string requestName, string targetNamespace, valuetype [mscorlib]System.Guid organizationId)
0x9e8  stloc.1
0x9e9  ldloc.0
0x9ea  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9ef  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9f4  ldarg.s  4
0x9f6  ldc.i4.1
0x9f7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x9fc  stloc.2
0x9fd  ldnull
0x9fe  stloc.3
0x9ff  ldarg.2
0xa00  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa05  brfalse.s loc_A10
0xa07  ldloc.1
0xa08  callvirt instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter Microsoft.Crm.Sdk.IRequestBuilder::get_TargetFilter()
0xa0d  stloc.3
0xa0e  br.s     loc_A19
0xa10  ldloc.1
0xa11  ldloc.2
0xa12  ldnull
0xa13  callvirt instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter Microsoft.Crm.Sdk.IRequestBuilder::GetCategoryFilter(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata primaryEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata secondaryEntity)
0xa18  stloc.3
0xa19  ldloc.2
0xa1a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0xa1f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0xa24  ldloc.2
0xa25  ldarg.1
0xa26  ldarg.s  4
0xa28  call     void Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfEntityNotFound(object entityDescriptor, string methodName, string entityName)
0xa2d  ldloc.2
0xa2e  ldarg.1
0xa2f  ldloc.3
0xa30  call     void Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfMethodNotSupported(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityDescriptor, string methodName, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageFilter filter)
0xa35  ret
```
