# Microsoft.Crm.Metadata.EntityService::CreateAuditingFields

- ea: `0x33b30`
- end: `0x33fcb`
- name: `Microsoft.Crm.Metadata.EntityService::CreateAuditingFields`
- size: `1179`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x33a90`

## callees

- `0x18d00`
- `0x190c0`
- `0x1c120`
- `0x1c130`
- `0x261b0`
- `0x33fd0`
- `0x43e10`
- `0x440f0`
- `0x44d40`
- `0x44d60`
- `0x44e50`
- `0x45010`
- `0x45430`
- `0x45450`

## string_xrefs

- `0x33b43`: `CreatedOn`
- `0x33b95`: `CreatedOnInfoDescription`
- `0x33bb6`: `CreatedOnInfoDisplayName`
- `0x33bf0`: `CreatedBy`
- `0x33faf`: `CreatedBy`
- `0x33c37`: `CreatedByInfoDescription`
- `0x33c58`: `CreatedByInfoDisplayName`
- `0x33e0b`: `CreatedOnBehalfBy`
- `0x33fb4`: `CreatedOnBehalfBy`
- `0x33e58`: `CreatedOnBehalfByInfoDescription`
- `0x33e7a`: `CreatedOnBehalfByInfoDisplayName`

## pseudocode

```c

```

## disassembly

```asm
0x33b30  ldarg.3
0x33b31  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.AttributeService::GetContextModifierOption(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x33b36  stloc.0
0x33b37  ldarg.1
0x33b38  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.IEntityInfo::get_EntityDescription()
0x33b3d  dup
0x33b3e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x33b43  ldstr    aCreatedon_0// "CreatedOn"
0x33b48  ldc.i4   0x1C000000
0x33b4d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x33b52  ldstr    aDatetime// "datetime"
0x33b57  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x33b5c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x33b61  ldarg.3
0x33b62  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x33b67  stloc.1
0x33b68  ldloc.1
0x33b69  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeFormats::get_DateTime()
0x33b6e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Format(string)
0x33b73  ldloc.1
0x33b74  ldc.i4.0
0x33b75  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifyAuditSettings(bool)
0x33b7a  ldloc.1
0x33b7b  ldc.i4.0
0x33b7c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsAuditEnabled(bool)
0x33b81  ldloc.1
0x33b82  ldarg.1
0x33b83  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.IEntityInfo::get_IntroducedVersion()
0x33b88  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x33b8d  ldloc.1
0x33b8e  ldc.i4.0
0x33b8f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifyBehavior(bool)
0x33b94  ldloc.1
0x33b95  ldstr    aCreatedoninfod// "CreatedOnInfoDescription"
0x33b9a  ldloc.1
0x33b9b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x33ba0  ldstr    aDescription// "Description"
0x33ba5  ldc.i4.1
0x33ba6  ldstr    aDescriptions// "Descriptions"
0x33bab  ldstr    aDescription// "Description"
0x33bb0  ldarg.3
0x33bb1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x33bb6  ldstr    aCreatedoninfod_0// "CreatedOnInfoDisplayName"
0x33bbb  ldloc.1
0x33bbc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x33bc1  ldstr    aDisplayname// "DisplayName"
0x33bc6  ldc.i4.1
0x33bc7  ldstr    aDisplaynames// "displaynames"
0x33bcc  ldstr    aDisplayname_0// "displayname"
0x33bd1  ldarg.3
0x33bd2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x33bd7  ldstr    aDatetime// "datetime"
0x33bdc  ldarg.3
0x33bdd  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::GetAttributeInfoFromAttributeDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection description, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection displayName, string typeName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x33be2  ldarg.2
0x33be3  ldarg.3
0x33be4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x33be9  pop
0x33bea  dup
0x33beb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x33bf0  ldstr    aCreatedby_1// "CreatedBy"
0x33bf5  ldc.i4   0x1C000000
0x33bfa  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x33bff  ldstr    aLookup// "lookup"
0x33c04  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x33c09  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x33c0e  ldarg.3
0x33c0f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x33c14  stloc.2
0x33c15  ldloc.2
0x33c16  ldc.i4.8
0x33c17  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ReferencedEntityObjectTypeCode(int32)
0x33c1c  ldloc.2
0x33c1d  ldc.i4.0
0x33c1e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifyAuditSettings(bool)
0x33c23  ldloc.2
0x33c24  ldc.i4.0
0x33c25  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsAuditEnabled(bool)
0x33c2a  ldloc.2
0x33c2b  ldarg.1
0x33c2c  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.IEntityInfo::get_IntroducedVersion()
0x33c31  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x33c36  ldloc.2
0x33c37  ldstr    aCreatedbyinfod// "CreatedByInfoDescription"
0x33c3c  ldloc.2
0x33c3d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x33c42  ldstr    aDescription// "Description"
0x33c47  ldc.i4.1
0x33c48  ldstr    aDescriptions// "Descriptions"
0x33c4d  ldstr    aDescription// "Description"
0x33c52  ldarg.3
0x33c53  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x33c58  ldstr    aCreatedbyinfod_0// "CreatedByInfoDisplayName"
0x33c5d  ldloc.2
0x33c5e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x33c63  ldstr    aDisplayname// "DisplayName"
0x33c68  ldc.i4.1
0x33c69  ldstr    aDisplaynames// "displaynames"
0x33c6e  ldstr    aDisplayname_0// "displayname"
0x33c73  ldarg.3
0x33c74  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x33c79  ldstr    aLookup// "lookup"
0x33c7e  ldarg.3
0x33c7f  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::GetAttributeInfoFromAttributeDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection description, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection displayName, string typeName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x33c84  dup
0x33c85  castclass Microsoft.Crm.Metadata.LookupAttributeInfo
0x33c8a  ldstr    aSingle// "single"
0x33c8f  callvirt instance void Microsoft.Crm.Metadata.LookupAttributeInfo::set_LookupStyle(string value)
0x33c94  ldarg.2
0x33c95  ldloc.0
0x33c96  ldarg.3
0x33c97  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifierOption, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x33c9c  pop
0x33c9d  dup
0x33c9e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x33ca3  ldstr    aModifiedon_0// "ModifiedOn"
0x33ca8  ldc.i4   0x1C000000
0x33cad  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x33cb2  ldstr    aDatetime// "datetime"
0x33cb7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x33cbc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x33cc1  ldarg.3
0x33cc2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x33cc7  stloc.3
0x33cc8  ldloc.3
0x33cc9  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeFormats::get_DateTime()
0x33cce  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Format(string)
0x33cd3  ldloc.3
0x33cd4  ldc.i4.0
0x33cd5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifyAuditSettings(bool)
0x33cda  ldloc.3
0x33cdb  ldc.i4.0
0x33cdc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsAuditEnabled(bool)
0x33ce1  ldloc.3
0x33ce2  ldarg.1
0x33ce3  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.IEntityInfo::get_IntroducedVersion()
0x33ce8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x33ced  ldloc.3
0x33cee  ldc.i4.0
0x33cef  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifyBehavior(bool)
0x33cf4  ldloc.3
0x33cf5  ldstr    aModifiedoninfo// "ModifiedOnInfoDescription"
0x33cfa  ldloc.3
0x33cfb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x33d00  ldstr    aDescription// "Description"
0x33d05  ldc.i4.1
0x33d06  ldstr    aDescriptions// "Descriptions"
0x33d0b  ldstr    aDescription// "Description"
0x33d10  ldarg.3
0x33d11  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x33d16  ldstr    aModifiedoninfo_0// "ModifiedOnInfoDisplayName"
0x33d1b  ldloc.3
0x33d1c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x33d21  ldstr    aDisplayname// "DisplayName"
0x33d26  ldc.i4.1
0x33d27  ldstr    aDisplaynames// "displaynames"
0x33d2c  ldstr    aDisplayname_0// "displayname"
0x33d31  ldarg.3
0x33d32  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x33d37  ldstr    aDatetime// "datetime"
0x33d3c  ldarg.3
0x33d3d  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::GetAttributeInfoFromAttributeDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection description, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection displayName, string typeName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x33d42  ldarg.2
0x33d43  ldarg.3
0x33d44  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x33d49  pop
0x33d4a  dup
0x33d4b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x33d50  ldstr    aModifiedby_0// "ModifiedBy"
0x33d55  ldc.i4   0x1C000000
0x33d5a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x33d5f  ldstr    aLookup// "lookup"
0x33d64  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x33d69  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x33d6e  ldarg.3
0x33d6f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x33d74  stloc.s  4
0x33d76  ldloc.s  4
0x33d78  ldc.i4.8
0x33d79  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ReferencedEntityObjectTypeCode(int32)
0x33d7e  ldloc.s  4
0x33d80  ldc.i4.0
0x33d81  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifyAuditSettings(bool)
0x33d86  ldloc.s  4
0x33d88  ldc.i4.0
0x33d89  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsAuditEnabled(bool)
0x33d8e  ldloc.s  4
0x33d90  ldarg.1
0x33d91  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.IEntityInfo::get_IntroducedVersion()
0x33d96  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x33d9b  ldloc.s  4
0x33d9d  ldstr    aModifiedbyinfo// "ModifiedByInfoDescription"
0x33da2  ldloc.s  4
0x33da4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x33da9  ldstr    aDescription// "Description"
0x33dae  ldc.i4.1
0x33daf  ldstr    aDescriptions// "Descriptions"
0x33db4  ldstr    aDescription// "Description"
0x33db9  ldarg.3
0x33dba  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x33dbf  ldstr    aModifiedbyinfo_0// "ModifiedByInfoDisplayName"
0x33dc4  ldloc.s  4
0x33dc6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x33dcb  ldstr    aDisplayname// "DisplayName"
0x33dd0  ldc.i4.1
0x33dd1  ldstr    aDisplaynames// "displaynames"
0x33dd6  ldstr    aDisplayname_0// "displayname"
0x33ddb  ldarg.3
0x33ddc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x33de1  ldstr    aLookup// "lookup"
0x33de6  ldarg.3
0x33de7  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::GetAttributeInfoFromAttributeDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection description, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection displayName, string typeName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x33dec  dup
0x33ded  castclass Microsoft.Crm.Metadata.LookupAttributeInfo
0x33df2  ldstr    aSingle// "single"
0x33df7  callvirt instance void Microsoft.Crm.Metadata.LookupAttributeInfo::set_LookupStyle(string value)
0x33dfc  ldarg.2
0x33dfd  ldloc.0
0x33dfe  ldarg.3
0x33dff  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifierOption, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x33e04  pop
0x33e05  dup
0x33e06  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x33e0b  ldstr    aCreatedonbehal_0// "CreatedOnBehalfBy"
0x33e10  ldc.i4   0x1C000000
0x33e15  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x33e1a  ldstr    aLookup// "lookup"
0x33e1f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x33e24  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x33e29  ldarg.3
0x33e2a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x33e2f  stloc.s  5
0x33e31  ldloc.s  5
0x33e33  ldc.i4.8
0x33e34  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ReferencedEntityObjectTypeCode(int32)
0x33e39  ldloc.s  5
0x33e3b  ldc.i4.0
0x33e3c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifyAuditSettings(bool)
0x33e41  ldloc.s  5
0x33e43  ldc.i4.0
0x33e44  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsAuditEnabled(bool)
0x33e49  ldloc.s  5
0x33e4b  ldarg.1
0x33e4c  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.IEntityInfo::get_IntroducedVersion()
0x33e51  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x33e56  ldloc.s  5
0x33e58  ldstr    aCreatedonbehal_1// "CreatedOnBehalfByInfoDescription"
0x33e5d  ldloc.s  5
0x33e5f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x33e64  ldstr    aDescription// "Description"
0x33e69  ldc.i4.1
0x33e6a  ldstr    aDescriptions// "Descriptions"
0x33e6f  ldstr    aDescription// "Description"
0x33e74  ldarg.3
0x33e75  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x33e7a  ldstr    aCreatedonbehal_2// "CreatedOnBehalfByInfoDisplayName"
0x33e7f  ldloc.s  5
0x33e81  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x33e86  ldstr    aDisplayname// "DisplayName"
0x33e8b  ldc.i4.1
0x33e8c  ldstr    aDisplaynames// "displaynames"
0x33e91  ldstr    aDisplayname_0// "displayname"
0x33e96  ldarg.3
0x33e97  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x33e9c  ldstr    aLookup// "lookup"
0x33ea1  ldarg.3
0x33ea2  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::GetAttributeInfoFromAttributeDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection description, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection displayName, string typeName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x33ea7  dup
0x33ea8  castclass Microsoft.Crm.Metadata.LookupAttributeInfo
0x33ead  ldstr    aSingle// "single"
0x33eb2  callvirt instance void Microsoft.Crm.Metadata.LookupAttributeInfo::set_LookupStyle(string value)
0x33eb7  ldarg.2
0x33eb8  ldloc.0
0x33eb9  ldarg.3
0x33eba  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifierOption, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x33ebf  pop
0x33ec0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x33ec5  ldstr    aModifiedonbeha_0// "ModifiedOnBehalfBy"
0x33eca  ldc.i4   0x1C000000
0x33ecf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x33ed4  ldstr    aLookup// "lookup"
0x33ed9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x33ede  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x33ee3  ldarg.3
0x33ee4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x33ee9  stloc.s  6
0x33eeb  ldloc.s  6
0x33eed  ldc.i4.8
0x33eee  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ReferencedEntityObjectTypeCode(int32)
0x33ef3  ldloc.s  6
0x33ef5  ldc.i4.0
0x33ef6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifyAuditSettings(bool)
0x33efb  ldloc.s  6
0x33efd  ldc.i4.0
0x33efe  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsAuditEnabled(bool)
0x33f03  ldloc.s  6
0x33f05  ldarg.1
0x33f06  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.IEntityInfo::get_IntroducedVersion()
0x33f0b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x33f10  ldloc.s  6
  ... truncated ...
```
