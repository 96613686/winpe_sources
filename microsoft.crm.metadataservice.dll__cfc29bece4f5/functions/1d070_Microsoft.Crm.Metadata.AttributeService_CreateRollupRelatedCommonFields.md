# Microsoft.Crm.Metadata.AttributeService::CreateRollupRelatedCommonFields

- ea: `0x1d070`
- end: `0x1d2ea`
- name: `Microsoft.Crm.Metadata.AttributeService::CreateRollupRelatedCommonFields`
- size: `634`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1c170`

## callees

- `0x184d0`
- `0x18760`
- `0x18d00`
- `0x1bdf0`
- `0x1d070`
- `0x1d620`
- `0x219b0`
- `0x255f0`
- `0x256e0`
- `0x256f0`
- `0x257d0`

## string_xrefs

- `0x1d1e8`: `lastUpdatedOnRollupFieldInfoDescription`
- `0x1d1ed`: `lastUpdatedOnRollupFieldInfoDisplayName`

## pseudocode

```c

```

## disassembly

```asm
0x1d070  ldarg.0
0x1d071  ldstr    aRollupfieldinf// "rollupFieldInfo"
0x1d076  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d07b  ldarg.1
0x1d07c  ldstr    aHelper// "helper"
0x1d081  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d086  ldarg.2
0x1d087  ldstr    aContext// "context"
0x1d08c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d091  ldarg.0
0x1d092  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1d097  stloc.0
0x1d098  ldarg.0
0x1d099  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1d09e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_PhysicalName()
0x1d0a3  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetLastUpdatedOnAttributePhysicalName(string)
0x1d0a8  stloc.1
0x1d0a9  ldarg.0
0x1d0aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1d0af  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_PhysicalName()
0x1d0b4  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.RollupSharedUtility::GetStateAttributePhysicalName(string)
0x1d0b9  stloc.2
0x1d0ba  ldloc.1
0x1d0bb  ldarg.0
0x1d0bc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x1d0c1  ldarg.2
0x1d0c2  call     void Microsoft.Crm.Metadata.AttributeService::CheckWhetherAttributeNameAlreadyExistsForStateAndDateFields(string attributeName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1d0c7  ldloc.2
0x1d0c8  ldarg.0
0x1d0c9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x1d0ce  ldarg.2
0x1d0cf  call     void Microsoft.Crm.Metadata.AttributeService::CheckWhetherAttributeNameAlreadyExistsForStateAndDateFields(string attributeName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1d0d4  ldarg.0
0x1d0d5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1d0da  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsBaseCurrency()
0x1d0df  brfalse.s loc_1D0E2
0x1d0e1  ret
0x1d0e2  ldarg.0
0x1d0e3  ldarg.2
0x1d0e4  call     bool Microsoft.Crm.Metadata.AttributeService::CanRollupValueBeCalculatedDeterministically(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1d0e9  ldarg.0
0x1d0ea  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x1d0ef  ldarg.2
0x1d0f0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1d0f5  ldarg.1
0x1d0f6  call     bool Microsoft.Crm.Metadata.AttributeService::IsCustomEntity(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x1d0fb  brfalse.s loc_1D108
0x1d0fd  ldarg.1
0x1d0fe  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x1d103  ldc.i4.0
0x1d104  ceq
0x1d106  br.s     loc_1D109
0x1d108  ldc.i4.0
0x1d109  stloc.3
0x1d10a  ldloc.3
0x1d10b  brfalse.s loc_1D114
0x1d10d  ldloc.1
0x1d10e  ldc.i4.1
0x1d10f  call     void Microsoft.Crm.Metadata.AttributeService::ValidateSchemaName(string name, bool allow1XPrefix)
0x1d114  ldarg.0
0x1d115  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x1d11a  ldloc.1
0x1d11b  ldc.i4   0x8000000
0x1d120  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x1d125  ldstr    aDatetime// "datetime"
0x1d12a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x1d12f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x1d134  ldarg.2
0x1d135  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x1d13a  stloc.s  4
0x1d13c  ldloc.s  4
0x1d13e  ldc.i4.1
0x1d13f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ValidForReadApi(bool)
0x1d144  ldloc.s  4
0x1d146  ldloc.0
0x1d147  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x1d14c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CalculationOf(valuetype [mscorlib]System.Guid)
0x1d151  ldloc.s  4
0x1d153  ldloc.0
0x1d154  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsCustomField()
0x1d159  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsCustomField(bool)
0x1d15e  ldloc.s  4
0x1d160  ldc.i4.1
0x1d161  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsStoredOnPrimaryTable(bool)
0x1d166  ldloc.s  4
0x1d168  ldloc.0
0x1d169  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IntroducedVersion()
0x1d16e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x1d173  ldloc.s  4
0x1d175  ldc.i4.0
0x1d176  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_SourceType(int32)
0x1d17b  ldloc.s  4
0x1d17d  ldloc.0
0x1d17e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsReplicated()
0x1d183  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsReplicated(bool)
0x1d188  ldloc.s  4
0x1d18a  ldc.i4.0
0x1d18b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsAuditEnabled(bool)
0x1d190  ldloc.s  4
0x1d192  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeFormats::get_DateTime()
0x1d197  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Format(string)
0x1d19c  ldloc.s  4
0x1d19e  ldloc.0
0x1d19f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsCustomizable()
0x1d1a4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsCustomizable(bool)
0x1d1a9  dup
0x1d1aa  call     string Microsoft.Crm.Metadata.AttributeService::GetRollupDateDefaultValue(bool canRollupValueBeCalculatedDeterministically)
0x1d1af  stloc.s  5
0x1d1b1  ldloc.s  5
0x1d1b3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d1b8  brfalse.s loc_1D1D2
0x1d1ba  ldloc.s  4
0x1d1bc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x1d1c1  ldstr    aDefaultvalue_0// "defaultvalue"
0x1d1c6  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1d1cb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1d1d0  br.s     loc_1D1E5
0x1d1d2  ldloc.s  4
0x1d1d4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x1d1d9  ldstr    aDefaultvalue_0// "defaultvalue"
0x1d1de  ldloc.s  5
0x1d1e0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1d1e5  ldloc.s  4
0x1d1e7  ldarg.0
0x1d1e8  ldstr    aLastupdatedonr// "lastUpdatedOnRollupFieldInfoDescription"
0x1d1ed  ldstr    aLastupdatedonr_0// "lastUpdatedOnRollupFieldInfoDisplayName"
0x1d1f2  ldc.i4.2
0x1d1f3  ldarg.1
0x1d1f4  ldarg.2
0x1d1f5  call     void Microsoft.Crm.Metadata.AttributeService::CreateAssociatedRollupRelatedfield(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag relatedAttributeInfoBag, class Microsoft.Crm.Metadata.AttributeInfo rollupFieldInfo, string localizedDescription, string localizedDisplayName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType relatedAttributeType, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1d1fa  ldloc.3
0x1d1fb  brfalse.s loc_1D204
0x1d1fd  ldloc.2
0x1d1fe  ldc.i4.1
0x1d1ff  call     void Microsoft.Crm.Metadata.AttributeService::ValidateSchemaName(string name, bool allow1XPrefix)
0x1d204  ldarg.0
0x1d205  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x1d20a  ldloc.2
0x1d20b  ldc.i4   0x8000000
0x1d210  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x1d215  ldstr    aInt// "int"
0x1d21a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x1d21f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x1d224  ldarg.2
0x1d225  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeDescription(valuetype [mscorlib]System.Guid entityId, string attributeName, int32 displayMask, valuetype [mscorlib]System.Guid attributeTypeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x1d22a  stloc.s  6
0x1d22c  ldloc.s  6
0x1d22e  ldc.i4.1
0x1d22f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ValidForReadApi(bool)
0x1d234  ldloc.s  6
0x1d236  ldloc.0
0x1d237  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x1d23c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CalculationOf(valuetype [mscorlib]System.Guid)
0x1d241  ldloc.s  6
0x1d243  ldloc.0
0x1d244  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsCustomField()
0x1d249  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsCustomField(bool)
0x1d24e  ldloc.s  6
0x1d250  ldc.i4.1
0x1d251  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsStoredOnPrimaryTable(bool)
0x1d256  ldloc.s  6
0x1d258  ldloc.0
0x1d259  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IntroducedVersion()
0x1d25e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IntroducedVersion(class [mscorlib]System.Version)
0x1d263  ldloc.s  6
0x1d265  ldc.i4.0
0x1d266  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_SourceType(int32)
0x1d26b  ldloc.s  6
0x1d26d  ldloc.0
0x1d26e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsReplicated()
0x1d273  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsReplicated(bool)
0x1d278  ldloc.s  6
0x1d27a  ldc.i4.0
0x1d27b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsAuditEnabled(bool)
0x1d280  ldloc.s  6
0x1d282  ldloc.0
0x1d283  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsCustomizable()
0x1d288  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsCustomizable(bool)
0x1d28d  ldloc.s  6
0x1d28f  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeFormats::get_None()
0x1d294  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_Format(string)
0x1d299  call     string Microsoft.Crm.Metadata.AttributeService::GetRollupStateDefaultValue(bool canRollupValueBeCalculatedDeterministically)
0x1d29e  stloc.s  7
0x1d2a0  ldloc.s  7
0x1d2a2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d2a7  brfalse.s loc_1D2C1
0x1d2a9  ldloc.s  6
0x1d2ab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x1d2b0  ldstr    aDefaultvalue_0// "defaultvalue"
0x1d2b5  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1d2ba  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1d2bf  br.s     loc_1D2D4
0x1d2c1  ldloc.s  6
0x1d2c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x1d2c8  ldstr    aDefaultvalue_0// "defaultvalue"
0x1d2cd  ldloc.s  7
0x1d2cf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x1d2d4  ldloc.s  6
0x1d2d6  ldarg.0
0x1d2d7  ldstr    aStaterollupfie// "stateRollupFieldInfoDescription"
0x1d2dc  ldstr    aStaterollupfie_0// "stateRollupFieldInfoDisplayName"
0x1d2e1  ldc.i4.5
0x1d2e2  ldarg.1
0x1d2e3  ldarg.2
0x1d2e4  call     void Microsoft.Crm.Metadata.AttributeService::CreateAssociatedRollupRelatedfield(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag relatedAttributeInfoBag, class Microsoft.Crm.Metadata.AttributeInfo rollupFieldInfo, string localizedDescription, string localizedDisplayName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType relatedAttributeType, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1d2e9  ret
```
