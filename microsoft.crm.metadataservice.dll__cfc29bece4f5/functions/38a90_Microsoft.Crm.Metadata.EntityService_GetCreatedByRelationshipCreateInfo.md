# Microsoft.Crm.Metadata.EntityService::GetCreatedByRelationshipCreateInfo

- ea: `0x38a90`
- end: `0x38bb4`
- name: `Microsoft.Crm.Metadata.EntityService::GetCreatedByRelationshipCreateInfo`
- size: `292`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `service_task, broker_com_uri`

## callers

- `0x32b80`
- `0x37ad0`

## callees

- `0x2eca0`
- `0x2ed30`
- `0x2ed80`
- `0x4c830`
- `0x4cdf0`
- `0x4ce10`
- `0x4ce30`
- `0x4ce50`
- `0x4ce90`
- `0x4ced0`
- `0x4cef0`
- `0x4cf10`
- `0x4cf70`
- `0x4cf90`
- `0x4cfb0`
- `0x4cff0`
- `0x4d010`
- `0x4d090`
- `0x4d0a0`
- `0x4d0c0`
- `0x4d0f0`
- `0x4d100`
- `0x4d110`
- `0x4d150`
- `0x4d230`

## string_xrefs

- `0x38ae8`: `createdby.label`
- `0x38b13`: `createdby.description`
- `0x38b35`: `CreatedByExternalParty`
- `0x38ba4`: `_createdby`

## pseudocode

```c

```

## disassembly

```asm
0x38a90  newobj   instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::.ctor()
0x38a95  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x38a9a  ldarg.1
0x38a9b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x38aa0  ldarg.1
0x38aa1  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x38aa6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x38aab  stloc.0
0x38aac  dup
0x38aad  ldc.i4.0
0x38aae  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeAssign(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType value)
0x38ab3  dup
0x38ab4  ldc.i4.2
0x38ab5  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeDelete(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType value)
0x38aba  dup
0x38abb  ldc.i4.0
0x38abc  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeReparent(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType value)
0x38ac1  dup
0x38ac2  ldc.i4.0
0x38ac3  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeShare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType value)
0x38ac8  dup
0x38ac9  ldc.i4.0
0x38aca  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeUnshare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType value)
0x38acf  dup
0x38ad0  ldstr    aExternalparty// "ExternalParty"
0x38ad5  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_PrimaryEntityName(string value)
0x38ada  ldloc.0
0x38adb  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x38ae0  stloc.1
0x38ae1  dup
0x38ae2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.RelationshipCreateInfo::get_PrimaryEntityInstanceName()
0x38ae7  ldloc.0
0x38ae8  ldstr    aCreatedbyLabel// "createdby.label"
0x38aed  ldloc.1
0x38aee  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x38af3  ldarg.1
0x38af4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x38af9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x38afe  dup
0x38aff  ldarg.0
0x38b00  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelatedEntityName(string value)
0x38b05  dup
0x38b06  ldc.i4.0
0x38b07  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeRequiredLevel(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel value)
0x38b0c  dup
0x38b0d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.RelationshipCreateInfo::get_Description()
0x38b12  ldloc.0
0x38b13  ldstr    aCreatedbyDescr// "createdby.description"
0x38b18  ldloc.1
0x38b19  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x38b1e  ldarg.1
0x38b1f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x38b24  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x38b29  dup
0x38b2a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x38b2f  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_LinkedAttributeId(valuetype [mscorlib]System.Guid value)
0x38b34  dup
0x38b35  ldstr    aCreatedbyexter// "CreatedByExternalParty"
0x38b3a  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeName(string value)
0x38b3f  dup
0x38b40  ldc.i4.0
0x38b41  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeIsSecured(bool value)
0x38b46  dup
0x38b47  ldc.i4.0
0x38b48  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeIsAuditEnabled(bool value)
0x38b4d  dup
0x38b4e  ldc.i4.1
0x38b4f  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipValidForAdvancedFind(bool value)
0x38b54  dup
0x38b55  ldc.i4.0
0x38b56  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeIsCustomizable(bool value)
0x38b5b  dup
0x38b5c  ldc.i4.0
0x38b5d  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_RelationshipAttributeIsCustomField(bool value)
0x38b62  dup
0x38b63  ldc.i4.0
0x38b64  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_IsHierarchical(bool value)
0x38b69  dup
0x38b6a  ldarg.1
0x38b6b  newobj   instance void Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x38b70  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_ReferencingEntityRoleInfo(class Microsoft.Crm.Metadata.EntityRelationshipRoleInfo value)
0x38b75  dup
0x38b76  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleInfo Microsoft.Crm.Metadata.RelationshipCreateInfo::get_ReferencingEntityRoleInfo()
0x38b7b  ldc.i4.2
0x38b7c  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::set_DisplayOption(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneDisplayOption value)
0x38b81  dup
0x38b82  callvirt instance class Microsoft.Crm.Metadata.EntityRelationshipRoleInfo Microsoft.Crm.Metadata.RelationshipCreateInfo::get_ReferencingEntityRoleInfo()
0x38b87  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::get_CustomLabels()
0x38b8c  ldloc.0
0x38b8d  ldsfld   string [mscorlib]System.String::Empty
0x38b92  ldarg.1
0x38b93  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x38b98  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x38b9d  dup
0x38b9e  ldstr    aLkExternalpart// "lk_externalparty_"
0x38ba3  ldarg.0
0x38ba4  ldstr    aCreatedby_3// "_createdby"
0x38ba9  call     string [mscorlib]System.String::Concat(string, string, string)
0x38bae  callvirt instance void Microsoft.Crm.Metadata.RelationshipCreateInfo::set_SchemaName(string value)
0x38bb3  ret
```
