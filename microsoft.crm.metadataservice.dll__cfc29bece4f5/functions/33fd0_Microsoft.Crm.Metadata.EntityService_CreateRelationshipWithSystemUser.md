# Microsoft.Crm.Metadata.EntityService::CreateRelationshipWithSystemUser

- ea: `0x33fd0`
- end: `0x3443d`
- name: `Microsoft.Crm.Metadata.EntityService::CreateRelationshipWithSystemUser`
- size: `1133`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x33b30`

## callees

- `0x18440`
- `0x18760`
- `0x18d00`
- `0x190c0`
- `0x1c130`
- `0x30a80`
- `0x33fd0`
- `0x34440`
- `0x34530`
- `0x44d30`
- `0x44d50`
- `0x44e50`
- `0x45010`
- `0x45420`
- `0x45440`

## string_xrefs

- `0x34014`: `CreatedByName`
- `0x340f6`: `CreatedByYomiName`
- `0x3411f`: `CreatedOnBehalfByName`
- `0x34201`: `CreatedOnBehalfByYomiName`

## pseudocode

```c

```

## disassembly

```asm
0x33fd0  ldarg.1
0x33fd1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.IEntityInfo::get_EntityDescription()
0x33fd6  stloc.0
0x33fd7  ldarg.s  7
0x33fd9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x33fde  ldstr    aSystemuser// "SystemUser"
0x33fe3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string)
0x33fe8  dup
0x33fe9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x33fee  stloc.1
0x33fef  dup
0x33ff0  ldstr    aFullname// "fullname"
0x33ff5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x33ffa  stloc.2
0x33ffb  dup
0x33ffc  ldstr    aYomifullname// "yomifullname"
0x34001  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x34006  stloc.3
0x34007  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKeyAttribute()
0x3400c  stloc.s  4
0x3400e  ldloc.0
0x3400f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x34014  ldstr    aCreatedbyname// "CreatedByName"
0x34019  ldc.i4.0
0x3401a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x3401f  ldstr    aNvarchar// "nvarchar"
0x34024  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x34029  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x3402e  ldarg.s  7
0x34030  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x34035  stloc.s  5
0x34037  ldloc.s  5
0x34039  ldc.i4.1
0x3403a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsLogical(bool)
0x3403f  ldloc.s  5
0x34041  ldc.i4.1
0x34042  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsSortAttribute(bool)
0x34047  ldloc.s  5
0x34049  ldarg.1
0x3404a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.IEntityInfo::get_CreatedByAttributeId()
0x3404f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AttributeOf(valuetype [mscorlib]System.Guid)
0x34054  ldloc.s  5
0x34056  ldstr    aName// "name"
0x3405b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_XmlAbbreviation(string)
0x34060  ldloc.s  5
0x34062  ldloc.2
0x34063  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Length()
0x34068  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Length(int32)
0x3406d  ldloc.s  5
0x3406f  ldc.i4.0
0x34070  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsAuditEnabled(bool)
0x34075  ldloc.s  5
0x34077  ldarg.1
0x34078  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.IEntityInfo::get_IntroducedVersion()
0x3407d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x34082  ldloc.s  5
0x34084  ldnull
0x34085  ldnull
0x34086  ldstr    aNvarchar// "nvarchar"
0x3408b  ldarg.s  7
0x3408d  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::GetAttributeInfoFromAttributeDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection description, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection displayName, string typeName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x34092  stloc.s  6
0x34094  ldloc.s  6
0x34096  ldarg.s  6
0x34098  ldarg.s  7
0x3409a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3409f  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_IsSystemContext()
0x340a4  brtrue.s loc_340B7
0x340a6  ldloc.s  6
0x340a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x340ad  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsLogical()
0x340b2  brfalse.s loc_340B7
0x340b4  ldc.i4.1
0x340b5  br.s     loc_340B8
0x340b7  ldc.i4.0
0x340b8  ldarg.s  7
0x340ba  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifierOption, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x340bf  pop
0x340c0  ldloc.0
0x340c1  ldarg.1
0x340c2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.IEntityInfo::get_CreatedByAttributeId()
0x340c7  ldarg.2
0x340c8  ldloc.1
0x340c9  ldloc.s  4
0x340cb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x340d0  ldarg.s  6
0x340d2  ldarg.s  7
0x340d4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag Microsoft.Crm.Metadata.EntityService::CreateRelationshipWithSystemUserHelper(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag referencingEntity, valuetype [mscorlib]System.Guid referencingAttributeId, string referencingAttributeName, valuetype [mscorlib]System.Guid systemUserEntityId, valuetype [mscorlib]System.Guid systemUserPrimaryKeyAttributeId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x340d9  stloc.s  7
0x340db  ldloc.s  7
0x340dd  ldloc.s  6
0x340df  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_AttributeId()
0x340e4  ldloc.2
0x340e5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x340ea  ldarg.s  6
0x340ec  ldarg.s  7
0x340ee  ldc.i4.1
0x340ef  call     void Microsoft.Crm.Metadata.EntityService::AddLogicalViewAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, valuetype [mscorlib]System.Guid attributeId, valuetype [mscorlib]System.Guid remoteAttributeId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool createIfNotExists)
0x340f4  ldarg.0
0x340f5  ldloc.0
0x340f6  ldstr    aCreatedbyyomin// "CreatedByYomiName"
0x340fb  ldloc.s  5
0x340fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x34102  ldarg.1
0x34103  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.IEntityInfo::get_CreatedByAttributeId()
0x34108  ldloc.s  7
0x3410a  ldloc.3
0x3410b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeDescription()
0x34110  ldarg.s  6
0x34112  ldarg.s  7
0x34114  call     instance void Microsoft.Crm.Metadata.EntityService::CreateYomiAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription entityInfo, string yomiAttributeName, valuetype [mscorlib]System.Guid yomiAttributeOf, valuetype [mscorlib]System.Guid attributeOf, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription remoteAttribute, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x34119  ldloc.0
0x3411a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x3411f  ldstr    aCreatedonbehal_3// "CreatedOnBehalfByName"
0x34124  ldc.i4.0
0x34125  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x3412a  ldstr    aNvarchar// "nvarchar"
0x3412f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x34134  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x34139  ldarg.s  7
0x3413b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x34140  stloc.s  8
0x34142  ldloc.s  8
0x34144  ldc.i4.1
0x34145  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsLogical(bool)
0x3414a  ldloc.s  8
0x3414c  ldc.i4.1
0x3414d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsSortAttribute(bool)
0x34152  ldloc.s  8
0x34154  ldarg.1
0x34155  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.IEntityInfo::get_CreatedByImpersonatorAttributeId()
0x3415a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AttributeOf(valuetype [mscorlib]System.Guid)
0x3415f  ldloc.s  8
0x34161  ldstr    aName// "name"
0x34166  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_XmlAbbreviation(string)
0x3416b  ldloc.s  8
0x3416d  ldloc.2
0x3416e  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Length()
0x34173  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Length(int32)
0x34178  ldloc.s  8
0x3417a  ldc.i4.0
0x3417b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsAuditEnabled(bool)
0x34180  ldloc.s  8
0x34182  ldarg.1
0x34183  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.IEntityInfo::get_IntroducedVersion()
0x34188  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x3418d  ldloc.s  8
0x3418f  ldnull
0x34190  ldnull
0x34191  ldstr    aNvarchar// "nvarchar"
0x34196  ldarg.s  7
0x34198  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::GetAttributeInfoFromAttributeDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection description, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection displayName, string typeName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x3419d  stloc.s  9
0x3419f  ldloc.s  9
0x341a1  ldarg.s  6
0x341a3  ldarg.s  7
0x341a5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x341aa  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_IsSystemContext()
0x341af  brtrue.s loc_341C2
0x341b1  ldloc.s  9
0x341b3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x341b8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsLogical()
0x341bd  brfalse.s loc_341C2
0x341bf  ldc.i4.1
0x341c0  br.s     loc_341C3
0x341c2  ldc.i4.0
0x341c3  ldarg.s  7
0x341c5  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifierOption, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x341ca  pop
0x341cb  ldloc.0
0x341cc  ldarg.1
0x341cd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.IEntityInfo::get_CreatedByImpersonatorAttributeId()
0x341d2  ldarg.3
0x341d3  ldloc.1
0x341d4  ldloc.s  4
0x341d6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x341db  ldarg.s  6
0x341dd  ldarg.s  7
0x341df  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag Microsoft.Crm.Metadata.EntityService::CreateRelationshipWithSystemUserHelper(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag referencingEntity, valuetype [mscorlib]System.Guid referencingAttributeId, string referencingAttributeName, valuetype [mscorlib]System.Guid systemUserEntityId, valuetype [mscorlib]System.Guid systemUserPrimaryKeyAttributeId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x341e4  stloc.s  0xA
0x341e6  ldloc.s  0xA
0x341e8  ldloc.s  9
0x341ea  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_AttributeId()
0x341ef  ldloc.2
0x341f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x341f5  ldarg.s  6
0x341f7  ldarg.s  7
0x341f9  ldc.i4.1
0x341fa  call     void Microsoft.Crm.Metadata.EntityService::AddLogicalViewAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, valuetype [mscorlib]System.Guid attributeId, valuetype [mscorlib]System.Guid remoteAttributeId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool createIfNotExists)
0x341ff  ldarg.0
0x34200  ldloc.0
0x34201  ldstr    aCreatedonbehal_4// "CreatedOnBehalfByYomiName"
0x34206  ldloc.s  8
0x34208  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x3420d  ldarg.1
0x3420e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.IEntityInfo::get_CreatedByImpersonatorAttributeId()
0x34213  ldloc.s  0xA
0x34215  ldloc.3
0x34216  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeDescription()
0x3421b  ldarg.s  6
0x3421d  ldarg.s  7
0x3421f  call     instance void Microsoft.Crm.Metadata.EntityService::CreateYomiAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription entityInfo, string yomiAttributeName, valuetype [mscorlib]System.Guid yomiAttributeOf, valuetype [mscorlib]System.Guid attributeOf, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription remoteAttribute, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x34224  ldloc.0
0x34225  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x3422a  ldstr    aModifiedbyname// "ModifiedByName"
0x3422f  ldc.i4.0
0x34230  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x34235  ldstr    aNvarchar// "nvarchar"
0x3423a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x3423f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x34244  ldarg.s  7
0x34246  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x3424b  stloc.s  0xB
0x3424d  ldloc.s  0xB
0x3424f  ldc.i4.1
0x34250  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsLogical(bool)
0x34255  ldloc.s  0xB
0x34257  ldc.i4.1
0x34258  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsSortAttribute(bool)
0x3425d  ldloc.s  0xB
0x3425f  ldarg.1
0x34260  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.IEntityInfo::get_ModifiedByAttributeId()
0x34265  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AttributeOf(valuetype [mscorlib]System.Guid)
0x3426a  ldloc.s  0xB
0x3426c  ldstr    aName// "name"
0x34271  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_XmlAbbreviation(string)
0x34276  ldloc.s  0xB
0x34278  ldloc.2
0x34279  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Length()
0x3427e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Length(int32)
0x34283  ldloc.s  0xB
0x34285  ldc.i4.0
0x34286  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsAuditEnabled(bool)
0x3428b  ldloc.s  0xB
0x3428d  ldarg.1
0x3428e  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Metadata.IEntityInfo::get_IntroducedVersion()
0x34293  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x34298  ldloc.s  0xB
0x3429a  ldnull
0x3429b  ldnull
0x3429c  ldstr    aNvarchar// "nvarchar"
0x342a1  ldarg.s  7
0x342a3  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::GetAttributeInfoFromAttributeDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection description, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection displayName, string typeName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x342a8  stloc.s  0xC
0x342aa  ldloc.s  0xC
0x342ac  ldarg.s  6
0x342ae  ldarg.s  7
0x342b0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x342b5  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_IsSystemContext()
0x342ba  brtrue.s loc_342CD
0x342bc  ldloc.s  0xC
0x342be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x342c3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsLogical()
0x342c8  brfalse.s loc_342CD
0x342ca  ldc.i4.1
0x342cb  br.s     loc_342CE
0x342cd  ldc.i4.0
0x342ce  ldarg.s  7
0x342d0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateInternal(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifierOption, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x342d5  pop
0x342d6  ldloc.0
0x342d7  ldarg.1
0x342d8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.IEntityInfo::get_ModifiedByAttributeId()
0x342dd  ldarg.s  4
0x342df  ldloc.1
0x342e0  ldloc.s  4
0x342e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x342e7  ldarg.s  6
0x342e9  ldarg.s  7
0x342eb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag Microsoft.Crm.Metadata.EntityService::CreateRelationshipWithSystemUserHelper(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag referencingEntity, valuetype [mscorlib]System.Guid referencingAttributeId, string referencingAttributeName, valuetype [mscorlib]System.Guid systemUserEntityId, valuetype [mscorlib]System.Guid systemUserPrimaryKeyAttributeId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x342f0  stloc.s  0xD
0x342f2  ldloc.s  0xD
0x342f4  ldloc.s  0xC
0x342f6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_AttributeId()
0x342fb  ldloc.2
0x342fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x34301  ldarg.s  6
0x34303  ldarg.s  7
0x34305  ldc.i4.1
0x34306  call     void Microsoft.Crm.Metadata.EntityService::AddLogicalViewAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, valuetype [mscorlib]System.Guid attributeId, valuetype [mscorlib]System.Guid remoteAttributeId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool createIfNotExists)
0x3430b  ldarg.0
0x3430c  ldloc.0
0x3430d  ldstr    aModifiedbyyomi// "ModifiedByYomiName"
0x34312  ldloc.s  0xB
0x34314  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x34319  ldarg.1
0x3431a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.IEntityInfo::get_ModifiedByAttributeId()
0x3431f  ldloc.s  0xD
0x34321  ldloc.3
0x34322  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeDescription()
0x34327  ldarg.s  6
0x34329  ldarg.s  7
0x3432b  call     instance void Microsoft.Crm.Metadata.EntityService::CreateYomiAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription entityInfo, string yomiAttributeName, valuetype [mscorlib]System.Guid yomiAttributeOf, valuetype [mscorlib]System.Guid attributeOf, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RelationshipDescriptionPropertyBag relationshipDescription, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription remoteAttribute, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x34330  ldloc.0
0x34331  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x34336  ldstr    aModifiedonbeha_3// "ModifiedOnBehalfByName"
0x3433b  ldc.i4.0
0x3433c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x34341  ldstr    aNvarchar// "nvarchar"
0x34346  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
  ... truncated ...
```
