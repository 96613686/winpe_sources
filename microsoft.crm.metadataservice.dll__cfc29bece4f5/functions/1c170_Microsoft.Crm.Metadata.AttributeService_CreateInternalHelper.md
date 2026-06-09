# Microsoft.Crm.Metadata.AttributeService::CreateInternalHelper

- ea: `0x1c170`
- end: `0x1c69f`
- name: `Microsoft.Crm.Metadata.AttributeService::CreateInternalHelper`
- size: `1327`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `service_task, broker_com_uri`

## callers

- `0x75790`

## callees

- `0x178d0`
- `0x18440`
- `0x18470`
- `0x18490`
- `0x184d0`
- `0x184f0`
- `0x18530`
- `0x18590`
- `0x18630`
- `0x18660`
- `0x18760`
- `0x187b0`
- `0x1be10`
- `0x1c170`
- `0x1c6a0`
- `0x1c6c0`
- `0x1c700`
- `0x1c8f0`
- `0x1cd20`
- `0x1d070`
- `0x1d2f0`
- `0x1d850`
- `0x1e140`
- `0x219b0`
- `0x22b30`
- `0x22fc0`
- `0x23300`
- `0x235e0`
- `0x238c0`
- `0x23af0`
- `0x261b0`
- `0x44120`
- `0x49d90`
- `0x49df0`
- `0x49e10`
- `0x59340`
- `0x59360`
- `0x5c910`

## string_xrefs

- `0x1c1d1`: `CheckExistingBeforeCreateForInternalSystemConvertedSolutions`
- `0x1c1e3`: `CheckExistingBeforeCreateForInternalSystemConvertedSolutions`

## pseudocode

```c

```

## disassembly

```asm
0x1c170  ldarg.0
0x1c171  ldstr    aAttributeinfo// "attributeInfo"
0x1c176  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1c17b  ldc.i4.0
0x1c17c  stloc.0
0x1c17d  ldstr    asc_804C0// ""
0x1c182  stloc.1
0x1c183  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x1c188  stloc.2
0x1c189  ldarg.0
0x1c18a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1c18f  stloc.3
0x1c190  ldarg.3
0x1c191  call     bool Microsoft.Crm.Metadata.UpgradeHelper::IsInUpdateViaCreateDuringUpgradeContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1c196  brfalse.s loc_1C1C3
0x1c198  ldloc.3
0x1c199  ldarg.3
0x1c19a  ldarg.1
0x1c19b  call     void Microsoft.Crm.Metadata.AttributeService::FixAttributePropertiesOverride(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x1c1a0  ldarg.0
0x1c1a1  ldarg.1
0x1c1a2  ldarg.3
0x1c1a3  ldarg.2
0x1c1a4  call     bool Microsoft.Crm.Metadata.AttributeService::TryUpdateAttributeInsteadOfCreate(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifier)
0x1c1a9  brtrue.s loc_1C1B6
0x1c1ab  ldarg.3
0x1c1ac  call     bool Microsoft.Crm.Metadata.UpgradeHelper::DoCreateIfExistingNotFoundInUpgradeContext(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1c1b1  brtrue   loc_1C247
0x1c1b6  ldarg.0
0x1c1b7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_AttributeId()
0x1c1bc  stloc.s  0xC
0x1c1be  leave    loc_1C69C
0x1c1c3  ldarg.1
0x1c1c4  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x1c1c9  brfalse.s loc_1C247
0x1c1cb  ldarg.3
0x1c1cc  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x1c1d1  ldstr    aCheckexistingb// "CheckExistingBeforeCreateForInternalSys"...
0x1c1d6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x1c1db  brfalse.s loc_1C247
0x1c1dd  ldarg.3
0x1c1de  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x1c1e3  ldstr    aCheckexistingb// "CheckExistingBeforeCreateForInternalSys"...
0x1c1e8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1c1ed  unbox.any [mscorlib]System.Boolean
0x1c1f2  brfalse.s loc_1C247
0x1c1f4  ldloc.3
0x1c1f5  ldarg.3
0x1c1f6  ldarg.1
0x1c1f7  call     void Microsoft.Crm.Metadata.AttributeService::FixAttributePropertiesOverride(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x1c1fc  ldarg.0
0x1c1fd  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x1c202  ldarg.0
0x1c203  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x1c208  ldloca.s 0xE
0x1c20a  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x1c210  ldloc.s  0xE
0x1c212  ldarg.3
0x1c213  ldc.i4.0
0x1c214  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Metadata.AttributeService::RetrieveAttributesByName(string name, valuetype [mscorlib]System.Guid entityId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> solutionId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool allColumns)
0x1c219  stloc.s  0xD
0x1c21b  ldloc.s  0xD
0x1c21d  brfalse.s loc_1C247
0x1c21f  ldloc.s  0xD
0x1c221  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x1c226  ldc.i4.0
0x1c227  ble.s    loc_1C247
0x1c229  ldloc.s  0xD
0x1c22b  ldc.i4.0
0x1c22c  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x1c231  ldstr    aAttributeid// "attributeid"
0x1c236  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1c23b  unbox.any [mscorlib]System.Guid
0x1c240  stloc.s  0xC
0x1c242  leave    loc_1C69C
0x1c247  ldarg.0
0x1c248  ldarg.1
0x1c249  ldarg.3
0x1c24a  call     void Microsoft.Crm.Metadata.AttributeService::SetCanBeSecuredFlags(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1c24f  ldarg.0
0x1c250  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::SetCreatePropertiesForCalculatedFields()
0x1c255  ldarg.0
0x1c256  callvirt instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsSecured()
0x1c25b  brfalse.s loc_1C28F
0x1c25d  ldloc.3
0x1c25e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_CanBeSecuredForCreate()
0x1c263  brtrue.s loc_1C28F
0x1c265  ldloc.3
0x1c266  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_CanBeSecuredForRead()
0x1c26b  brtrue.s loc_1C28F
0x1c26d  ldloc.3
0x1c26e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_CanBeSecuredForUpdate()
0x1c273  brtrue.s loc_1C28F
0x1c275  ldc.i4   0x8004F501
0x1c27a  ldc.i4.1
0x1c27b  newarr   [mscorlib]System.Object
0x1c280  dup
0x1c281  ldc.i4.0
0x1c282  ldarg.0
0x1c283  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x1c288  stelem.ref
0x1c289  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1c28e  throw
0x1c28f  ldarg.0
0x1c290  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x1c295  ldarg.1
0x1c296  ldc.i4.1
0x1c297  newarr   [mscorlib]System.String
0x1c29c  dup
0x1c29d  ldc.i4.0
0x1c29e  ldstr    aDataproviderid// "dataproviderid"
0x1c2a3  stelem.ref
0x1c2a4  ldarg.3
0x1c2a5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1c2aa  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription Microsoft.Crm.Metadata.AttributeService::GetParentEntity(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, string[] columnNames, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x1c2af  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_DataProviderId()
0x1c2b4  stloc.s  0xE
0x1c2b6  ldloca.s 0xE
0x1c2b8  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x1c2bd  stloc.s  4
0x1c2bf  ldnull
0x1c2c0  stloc.s  6
0x1c2c2  ldnull
0x1c2c3  stloc.s  7
0x1c2c5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c2ca  stloc.s  8
0x1c2cc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c2d1  stloc.s  9
0x1c2d3  ldarg.0
0x1c2d4  isinst   Microsoft.Crm.Metadata.EnumAttributeInfo
0x1c2d9  dup
0x1c2da  stloc.s  5
0x1c2dc  brfalse.s loc_1C2EC
0x1c2de  ldloc.s  5
0x1c2e0  ldarg.1
0x1c2e1  ldarg.3
0x1c2e2  call     void Microsoft.Crm.Metadata.AttributeService::CreateOptionSet(class Microsoft.Crm.Metadata.EnumAttributeInfo enumInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1c2e7  br       loc_1C438
0x1c2ec  ldarg.0
0x1c2ed  isinst   Microsoft.Crm.Metadata.ImageAttributeInfo
0x1c2f2  dup
0x1c2f3  stloc.s  6
0x1c2f5  brfalse  loc_1C438
0x1c2fa  ldarg.0
0x1c2fb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeInfo::get_EntityId()
0x1c300  ldarg.3
0x1c301  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1c306  ldarg.1
0x1c307  call     bool Microsoft.Crm.Metadata.AttributeService::IsCustomEntity(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x1c30c  brtrue.s loc_1C319
0x1c30e  ldarg.1
0x1c30f  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x1c314  ldc.i4.0
0x1c315  ceq
0x1c317  br.s     loc_1C31A
0x1c319  ldc.i4.1
0x1c31a  stloc.s  0xF
0x1c31c  ldloc.s  6
0x1c31e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1c323  ldarg.3
0x1c324  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1c329  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.ImageAttributeHelper::GetImageIdFieldAttributeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription attributeDescription, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x1c32e  stloc.s  7
0x1c330  ldloc.s  7
0x1c332  ldloc.s  0xF
0x1c334  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsCustomField(bool)
0x1c339  ldloc.s  7
0x1c33b  ldarg.3
0x1c33c  ldarg.1
0x1c33d  call     void Microsoft.Crm.Metadata.AttributeService::FixAttributePropertiesOverride(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x1c342  ldarg.1
0x1c343  ldloc.s  7
0x1c345  ldc.i4.0
0x1c346  ldarg.2
0x1c347  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption)
0x1c34c  ldloc.s  6
0x1c34e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1c353  ldc.i4.1
0x1c354  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsLogical(bool)
0x1c359  ldloc.s  6
0x1c35b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1c360  ldloc.s  7
0x1c362  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x1c367  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AttributeOf(valuetype [mscorlib]System.Guid)
0x1c36c  ldloc.s  6
0x1c36e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1c373  ldstr    aImg// "img"
0x1c378  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_XmlAbbreviation(string)
0x1c37d  ldloc.s  6
0x1c37f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1c384  ldc.i4   0x1800000
0x1c389  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x1c38e  ldloc.s  6
0x1c390  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1c395  ldc.i4.0
0x1c396  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifySearchSettings(bool)
0x1c39b  ldloc.s  6
0x1c39d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1c3a2  ldc.i4.0
0x1c3a3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_CanModifyRequirementLevelSettings(bool)
0x1c3a8  ldloc.s  6
0x1c3aa  ldc.i4.0
0x1c3ab  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::.ctor(var<u1>)
0x1c3b0  callvirt instance void Microsoft.Crm.Metadata.AttributeInfo::set_RequiredLevel(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel> value)
0x1c3b5  ldloc.s  6
0x1c3b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1c3bc  call     void Microsoft.Crm.Metadata.SavedQueryHelper::SetExternalSearchAttributePropertyValuesForNewAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeDescription)
0x1c3c1  ldloc.s  6
0x1c3c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1c3c8  ldarg.3
0x1c3c9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1c3ce  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.ImageAttributeHelper::GetImageUrlFieldAttributeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription attributeDescription, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x1c3d3  stloc.s  0x10
0x1c3d5  ldloc.s  0x10
0x1c3d7  ldloc.s  0xF
0x1c3d9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsCustomField(bool)
0x1c3de  ldloc.s  0x10
0x1c3e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x1c3e5  stloc.s  8
0x1c3e7  ldloc.s  0x10
0x1c3e9  ldarg.3
0x1c3ea  ldarg.1
0x1c3eb  call     void Microsoft.Crm.Metadata.AttributeService::FixAttributePropertiesOverride(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x1c3f0  ldarg.1
0x1c3f1  ldloc.s  0x10
0x1c3f3  ldc.i4.0
0x1c3f4  ldarg.2
0x1c3f5  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption)
0x1c3fa  ldloc.s  0x10
0x1c3fc  call     void Microsoft.Crm.Metadata.SavedQueryHelper::SetExternalSearchAttributePropertyValuesForNewAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeDescription)
0x1c401  ldloc.s  6
0x1c403  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1c408  ldarg.3
0x1c409  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1c40e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.ImageAttributeHelper::GetImageTimestampFieldAttributeInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription attributeDescription, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x1c413  stloc.s  0x10
0x1c415  ldloc.s  0x10
0x1c417  ldloc.s  0xF
0x1c419  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_IsCustomField(bool)
0x1c41e  ldloc.s  0x10
0x1c420  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x1c425  stloc.s  9
0x1c427  ldarg.1
0x1c428  ldloc.s  0x10
0x1c42a  ldc.i4.0
0x1c42b  ldarg.2
0x1c42c  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption)
0x1c431  ldloc.s  0x10
0x1c433  call     void Microsoft.Crm.Metadata.SavedQueryHelper::SetExternalSearchAttributePropertyValuesForNewAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeDescription)
0x1c438  ldloc.3
0x1c439  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AutoNumberFormat()
0x1c43e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1c443  brtrue.s loc_1C45F
0x1c445  ldloc.3
0x1c446  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsCustomField()
0x1c44b  brfalse.s loc_1C45F
0x1c44d  ldloc.3
0x1c44e  dup
0x1c44f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_DisplayMask()
0x1c454  ldc.i4   0x400000
0x1c459  or
0x1c45a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x1c45f  ldloc.3
0x1c460  ldarg.3
0x1c461  ldarg.1
0x1c462  call     void Microsoft.Crm.Metadata.AttributeService::FixAttributePropertiesOverride(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeDescription, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x1c467  ldarg.1
0x1c468  ldloc.3
0x1c469  ldc.i4.0
0x1c46a  ldarg.0
0x1c46b  ldarg.1
0x1c46c  ldarg.2
0x1c46d  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.AttributeService::GetModifierForChildAttribute(class Microsoft.Crm.Metadata.AttributeInfo attribute, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper mh, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption modifier)
0x1c472  ldloc.s  4
0x1c474  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddToQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription, valuetype [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.ActionType, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption, bool)
0x1c479  ldarg.0
0x1c47a  ldnull
0x1c47b  ldarg.3
0x1c47c  call     void Microsoft.Crm.Metadata.AttributeService::ProcessSourceTypeRules(class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity existingAttributeData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1c481  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Metadata.AttributeService::ValidTypesForChildAttributes
0x1c486  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesById()
0x1c48b  ldloc.3
0x1c48c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeTypeId()
0x1c491  box      [mscorlib]System.Guid
0x1c496  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x1c49b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x1c4a0  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x1c4a5  brfalse.s loc_1C4B6
0x1c4a7  ldloc.3
0x1c4a8  ldarg.3
0x1c4a9  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption Microsoft.Crm.Metadata.AttributeService::GetContextModifierOption(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1c4ae  ldarg.1
0x1c4af  ldarg.3
0x1c4b0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::CreateChildAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeDescription, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ContextModifierOption option, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1c4b5  pop
0x1c4b6  ldloc.3
0x1c4b7  call     void Microsoft.Crm.Metadata.SavedQueryHelper::SetExternalSearchAttributePropertyValuesForNewAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag attributeDescription)
0x1c4bc  ldloc.3
0x1c4bd  ldarg.3
0x1c4be  ldarg.1
  ... truncated ...
```
