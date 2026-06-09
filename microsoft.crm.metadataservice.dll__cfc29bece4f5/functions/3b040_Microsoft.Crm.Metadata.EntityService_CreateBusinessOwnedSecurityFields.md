# Microsoft.Crm.Metadata.EntityService::CreateBusinessOwnedSecurityFields

- ea: `0x3b040`
- end: `0x3b258`
- name: `Microsoft.Crm.Metadata.EntityService::CreateBusinessOwnedSecurityFields`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x3add0`

## callees

- `0x18440`
- `0x18590`
- `0x18d00`
- `0x190c0`
- `0x1c120`
- `0x1c130`
- `0x261b0`
- `0x3b260`
- `0x43e10`
- `0x44e50`
- `0x45010`

## string_xrefs

- `0x3b13b`: `BusinessIdInfoDescription`
- `0x3b15c`: `BusinessIdInfoDisplayName`

## pseudocode

```c

```

## disassembly

```asm
0x3b040  ldarg.1
0x3b041  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.IEntityInfo::get_EntityDescription()
0x3b046  stloc.0
0x3b047  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::.ctor()
0x3b04c  ldstr    aBusinessunit// "BusinessUnit"
0x3b051  ldstr    aEntity_0// "Entity"
0x3b056  ldc.i4.3
0x3b057  newarr   [mscorlib]System.String
0x3b05c  dup
0x3b05d  ldc.i4.0
0x3b05e  ldstr    aEntityid// "entityid"
0x3b063  stelem.ref
0x3b064  dup
0x3b065  ldc.i4.1
0x3b066  ldstr    aLogicalname// "logicalname"
0x3b06b  stelem.ref
0x3b06c  dup
0x3b06d  ldc.i4.2
0x3b06e  ldstr    aObjecttypecode_0// "objecttypecode"
0x3b073  stelem.ref
0x3b074  ldarg.3
0x3b075  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3b07a  ldarg.3
0x3b07b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3b080  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::RetrieveByNameAsIfPublished(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x3b085  stloc.1
0x3b086  ldloc.1
0x3b087  ldstr    aEntityid// "entityid"
0x3b08c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3b091  unbox.any [mscorlib]System.Guid
0x3b096  stloc.2
0x3b097  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::.ctor()
0x3b09c  ldloc.2
0x3b09d  ldstr    aAttribute// "Attribute"
0x3b0a2  ldc.i4.1
0x3b0a3  newarr   [mscorlib]System.String
0x3b0a8  dup
0x3b0a9  ldc.i4.0
0x3b0aa  ldstr    aAttributeid// "attributeid"
0x3b0af  stelem.ref
0x3b0b0  ldarg.3
0x3b0b1  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3b0b6  ldarg.3
0x3b0b7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3b0bc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::RetrievePrimaryKeyAttributeAsIfPublished(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x3b0c1  ldstr    aAttributeid// "attributeid"
0x3b0c6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3b0cb  unbox.any [mscorlib]System.Guid
0x3b0d0  pop
0x3b0d1  ldloc.0
0x3b0d2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x3b0d7  ldstr    aBusinessunitid_0// "BusinessUnitId"
0x3b0dc  ldc.i4.0
0x3b0dd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x3b0e2  ldstr    aLookup// "lookup"
0x3b0e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x3b0ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x3b0f1  ldarg.3
0x3b0f2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x3b0f7  stloc.3
0x3b0f8  ldloc.3
0x3b0f9  ldc.i4.1
0x3b0fa  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ValidForUpdateApi(bool)
0x3b0ff  ldloc.3
0x3b100  ldc.i4.1
0x3b101  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ValidForCreateApi(bool)
0x3b106  ldloc.3
0x3b107  ldarg.1
0x3b108  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.IEntityInfo::get_IntroducedVersion()
0x3b10d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x3b112  ldloc.3
0x3b113  ldstr    aSingle// "single"
0x3b118  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_LookupStyle(string)
0x3b11d  ldloc.3
0x3b11e  ldloc.1
0x3b11f  ldstr    aObjecttypecode_0// "objecttypecode"
0x3b124  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3b129  unbox.any [mscorlib]System.Int32
0x3b12e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ReferencedEntityObjectTypeCode(int32)
0x3b133  ldloc.3
0x3b134  ldc.i4.0
0x3b135  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifyRequirementLevelSettings(bool)
0x3b13a  ldloc.3
0x3b13b  ldstr    aBusinessidinfo// "BusinessIdInfoDescription"
0x3b140  ldloc.3
0x3b141  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x3b146  ldstr    aDescription// "Description"
0x3b14b  ldc.i4.1
0x3b14c  ldstr    aDescriptions// "Descriptions"
0x3b151  ldstr    aDescription// "Description"
0x3b156  ldarg.3
0x3b157  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3b15c  ldstr    aBusinessidinfo_0// "BusinessIdInfoDisplayName"
0x3b161  ldloc.3
0x3b162  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x3b167  ldstr    aDisplayname// "DisplayName"
0x3b16c  ldc.i4.1
0x3b16d  ldstr    aDisplaynames// "displaynames"
0x3b172  ldstr    aDisplayname_0// "displayname"
0x3b177  ldarg.3
0x3b178  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.LocalizationHelper::GetLabelsForResource(string resourceName, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string collectionName, string labelName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3b17d  ldstr    aUniqueidentifi// "uniqueidentifier"
0x3b182  ldarg.3
0x3b183  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::GetAttributeInfoFromAttributeDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection description, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection displayName, string typeName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x3b188  stloc.s  4
0x3b18a  ldloc.s  4
0x3b18c  ldc.i4.1
0x3b18d  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::.ctor(var<u1>)
0x3b192  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::set_RequiredLevel(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel> value)
0x3b197  ldloc.s  4
0x3b199  ldarg.2
0x3b19a  ldarg.3
0x3b19b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3b1a0  pop
0x3b1a1  ldloc.0
0x3b1a2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x3b1a7  ldstr    aBusinessunitid_1// "BusinessUnitIdName"
0x3b1ac  ldc.i4.0
0x3b1ad  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x3b1b2  ldstr    aNvarchar// "nvarchar"
0x3b1b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x3b1bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x3b1c1  ldarg.3
0x3b1c2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x3b1c7  stloc.s  5
0x3b1c9  ldloc.s  5
0x3b1cb  ldc.i4.1
0x3b1cc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsLogical(bool)
0x3b1d1  ldloc.s  5
0x3b1d3  ldc.i4.1
0x3b1d4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsSortAttribute(bool)
0x3b1d9  ldloc.s  5
0x3b1db  ldc.i4.0
0x3b1dc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsNullable(bool)
0x3b1e1  ldloc.s  5
0x3b1e3  ldstr    aName// "name"
0x3b1e8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_XmlAbbreviation(string)
0x3b1ed  ldloc.s  5
0x3b1ef  ldc.i4   0x140
0x3b1f4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Length(int32)
0x3b1f9  ldloc.s  5
0x3b1fb  ldloc.s  4
0x3b1fd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_AttributeId()
0x3b202  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AttributeOf(valuetype [mscorlib]System.Guid)
0x3b207  ldloc.s  5
0x3b209  ldarg.1
0x3b20a  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.IEntityInfo::get_IntroducedVersion()
0x3b20f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x3b214  ldloc.s  5
0x3b216  ldc.i4.0
0x3b217  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifyRequirementLevelSettings(bool)
0x3b21c  ldloc.s  5
0x3b21e  ldnull
0x3b21f  ldnull
0x3b220  ldstr    aNvarchar// "nvarchar"
0x3b225  ldarg.3
0x3b226  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::GetAttributeInfoFromAttributeDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection description, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection displayName, string typeName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x3b22b  ldarg.2
0x3b22c  ldarg.3
0x3b22d  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.AttributeService::GetContextModifierOption(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3b232  ldarg.3
0x3b233  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifierOption, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3b238  pop
0x3b239  ldarg.0
0x3b23a  ldarg.1
0x3b23b  ldarg.2
0x3b23c  ldloc.1
0x3b23d  ldloc.0
0x3b23e  ldloc.3
0x3b23f  ldloc.s  5
0x3b241  ldstr    aBusinessUnit// "business_unit_"
0x3b246  ldloc.0
0x3b247  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_LogicalName()
0x3b24c  call     string [mscorlib]System.String::Concat(string, string)
0x3b251  ldarg.3
0x3b252  call     instance void Microsoft.Crm.Metadata.EntityService::CreateRelationshipServiceInfo(class Microsoft.Crm.Metadata.IEntityInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity metadataBusinessUnitEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag entityDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag businessIdAttribute, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag idNameAttributeProperty, string relationshipName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3b257  ret
```
