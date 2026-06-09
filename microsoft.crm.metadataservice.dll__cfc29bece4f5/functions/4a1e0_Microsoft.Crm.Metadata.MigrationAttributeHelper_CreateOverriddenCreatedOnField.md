# Microsoft.Crm.Metadata.MigrationAttributeHelper::CreateOverriddenCreatedOnField

- ea: `0x4a1e0`
- end: `0x4a2b7`
- name: `Microsoft.Crm.Metadata.MigrationAttributeHelper::CreateOverriddenCreatedOnField`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x35560`

## callees

- `0x18d00`
- `0x190c0`
- `0x1c120`
- `0x43e10`

## string_xrefs

- `0x4a20c`: `OverriddenCreatedOn`
- `0x4a261`: `OverriddenCreatedOnDescription`
- `0x4a282`: `OverriddenCreatedOnDisplayName`

## pseudocode

```c

```

## disassembly

```asm
0x4a1e0  ldarg.0
0x4a1e1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x4a1e6  ldstr    aEntityid_0// "entityId"
0x4a1eb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x4a1f0  ldarg.1
0x4a1f1  ldstr    aMetadatahelper// "metadataHelper"
0x4a1f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4a1fb  ldarg.3
0x4a1fc  ldstr    aContext// "context"
0x4a201  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4a206  ldarg.0
0x4a207  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x4a20c  ldstr    aOverriddencrea_0// "OverriddenCreatedOn"
0x4a211  ldc.i4   0x14000000
0x4a216  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x4a21b  ldstr    aDatetime// "datetime"
0x4a220  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x4a225  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x4a22a  ldarg.3
0x4a22b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x4a230  stloc.0
0x4a231  ldloc.0
0x4a232  ldc.i4.1
0x4a233  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ValidForCreateApi(bool)
0x4a238  ldloc.0
0x4a239  ldc.i4.0
0x4a23a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ValidForUpdateApi(bool)
0x4a23f  ldloc.0
0x4a240  ldc.i4.1
0x4a241  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ValidForReadApi(bool)
0x4a246  ldloc.0
0x4a247  ldc.i4.0
0x4a248  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifyBehavior(bool)
0x4a24d  ldloc.0
0x4a24e  ldarg.2
0x4a24f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_TableColumnName(string)
0x4a254  ldloc.0
0x4a255  ldarg.0
0x4a256  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IntroducedVersion()
0x4a25b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x4a260  ldloc.0
0x4a261  ldstr    aOverriddencrea_1// "OverriddenCreatedOnDescription"
0x4a266  ldloc.0
0x4a267  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x4a26c  ldstr    aDescription// "Description"
0x4a271  ldc.i4.1
0x4a272  ldstr    aDescriptions// "Descriptions"
0x4a277  ldstr    aDescription// "Description"
0x4a27c  ldarg.3
0x4a27d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4a282  ldstr    aOverriddencrea_2// "OverriddenCreatedOnDisplayName"
0x4a287  ldloc.0
0x4a288  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x4a28d  ldstr    aDisplayname// "DisplayName"
0x4a292  ldc.i4.1
0x4a293  ldstr    aDisplaynames// "displaynames"
0x4a298  ldstr    aDisplayname_0// "displayname"
0x4a29d  ldarg.3
0x4a29e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4a2a3  ldstr    aDatetime// "datetime"
0x4a2a8  ldarg.3
0x4a2a9  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::GetAttributeInfoFromAttributeDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection description, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection displayName, string typeName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x4a2ae  ldarg.1
0x4a2af  ldarg.3
0x4a2b0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4a2b5  pop
0x4a2b6  ret
```
