# Microsoft.Crm.Metadata.EntityService::UpdateInternal

- ea: `0x37ad0`
- end: `0x387ef`
- name: `Microsoft.Crm.Metadata.EntityService::UpdateInternal`
- size: `3359`
- prototype: ``
- caller_count: `1`
- callee_count: `57`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x76730`

## callees

- `0x310b0`
- `0x33180`
- `0x34ab0`
- `0x36930`
- `0x36a70`
- `0x36b40`
- `0x36c30`
- `0x374b0`
- `0x37700`
- `0x37890`
- `0x37ad0`
- `0x387f0`
- `0x38860`
- `0x38a30`
- `0x38a90`
- `0x38bc0`
- `0x39220`
- `0x39510`
- `0x39600`
- `0x39620`
- `0x3ab10`
- `0x3acd0`
- `0x3c020`
- `0x3cc20`
- `0x3cc80`
- `0x3cca0`
- `0x3ce40`
- `0x3cee0`
- `0x3cf00`
- `0x3cf60`
- `0x3cf70`
- `0x3d020`
- `0x3d1b0`
- `0x3d610`
- `0x3d770`
- `0x3d7b0`
- `0x496d0`
- `0x4d140`
- `0x4edf0`
- `0x50490`
- `0x50e80`
- `0x565f0`
- `0x56760`
- `0x57120`
- `0x571a0`
- `0x57bc0`
- `0x59320`
- `0x593c0`
- `0x59420`
- `0x5aa60`

## string_xrefs

- `0x37cdf`: `autocreateaccessteams`
- `0x37d27`: `autocreateaccessteams`
- `0x3800a`: `Cannot disable autocreateaccessteams property for entity {0} while associated team templates exist`

## pseudocode

```c

```

## disassembly

```asm
0x37ad0  newobj   instance void <>c__DisplayClass166_0::.ctor()
0x37ad5  stloc.0
0x37ad6  ldloc.0
0x37ad7  ldarg.0
0x37ad8  stfld    class Microsoft.Crm.Metadata.EntityService <>c__DisplayClass166_0::<>4__this
0x37add  ldloc.0
0x37ade  ldarg.2
0x37adf  stfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass166_0::entityInfo
0x37ae4  ldloc.0
0x37ae5  ldarg.s  4
0x37ae7  stfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass166_0::metadataHelper
0x37aec  ldloc.0
0x37aed  ldarg.3
0x37aee  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass166_0::context
0x37af3  ldc.i4.0
0x37af4  stloc.1
0x37af5  ldstr    asc_804C0// ""
0x37afa  stloc.2
0x37afb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x37b00  stloc.3
0x37b01  newobj   instance void <>c__DisplayClass166_1::.ctor()
0x37b06  stloc.s  4
0x37b08  ldloc.s  4
0x37b0a  ldloc.0
0x37b0b  stfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37b10  ldloc.s  4
0x37b12  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37b17  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass166_0::entityInfo
0x37b1c  ldarg.1
0x37b1d  callvirt instance void Microsoft.Crm.Metadata.EntityUpdateInfo::set_EntityId(valuetype [mscorlib]System.Guid value)
0x37b22  ldc.i4.1
0x37b23  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IEntityFacadeBridge [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.EntityFacadeBridgeFactory::Create(int32)
0x37b28  ldarg.1
0x37b29  ldloc.s  4
0x37b2b  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37b30  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass166_0::context
0x37b35  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IEntityFacadeBridge::RetrieveEntity(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x37b3a  stloc.s  5
0x37b3c  ldloc.s  5
0x37b3e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity::get_InnerEntity()
0x37b43  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity
0x37b48  stloc.s  6
0x37b4a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::.ctor()
0x37b4f  stloc.s  7
0x37b51  ldnull
0x37b52  stloc.s  8
0x37b54  ldloc.s  7
0x37b56  ldarg.1
0x37b57  ldstr    aAttribute// "Attribute"
0x37b5c  ldc.i4.2
0x37b5d  newarr   [mscorlib]System.String
0x37b62  dup
0x37b63  ldc.i4.0
0x37b64  ldstr    aAttributeid// "attributeid"
0x37b69  stelem.ref
0x37b6a  dup
0x37b6b  ldc.i4.1
0x37b6c  ldstr    aIslogical// "islogical"
0x37b71  stelem.ref
0x37b72  ldloc.s  4
0x37b74  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37b79  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass166_0::context
0x37b7e  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x37b83  ldloc.s  4
0x37b85  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37b8a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass166_0::context
0x37b8f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x37b94  ldloca.s 8
0x37b96  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::TryRetrievePrimaryFieldAttributeAsIfPublished(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity&)
0x37b9b  pop
0x37b9c  ldloc.s  5
0x37b9e  ldloc.s  4
0x37ba0  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37ba5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass166_0::context
0x37baa  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IsManagedCondition::IsEntityManaged(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x37baf  stloc.s  9
0x37bb1  ldarg.0
0x37bb2  ldloc.s  4
0x37bb4  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37bb9  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass166_0::entityInfo
0x37bbe  ldloc.s  6
0x37bc0  ldloc.s  8
0x37bc2  ldloc.s  4
0x37bc4  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37bc9  ldfld    class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper <>c__DisplayClass166_0::metadataHelper
0x37bce  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x37bd3  ldloc.s  9
0x37bd5  ldarg.s  5
0x37bd7  ldloc.s  4
0x37bd9  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37bde  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass166_0::context
0x37be3  callvirt instance void Microsoft.Crm.Metadata.EntityService::ValidateForUpdate(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity primaryFieldAttribute, bool isInternalSolutionContext, bool isExistingEntityManaged, bool mergeLabels, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x37be8  ldloc.s  6
0x37bea  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x37bef  stloc.s  0xA
0x37bf1  ldloc.s  4
0x37bf3  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37bf8  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass166_0::entityInfo
0x37bfd  callvirt instance string Microsoft.Crm.Metadata.EntityUpdateInfo::get_LogicalName()
0x37c02  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x37c07  brfalse.s loc_37C21
0x37c09  ldloc.s  4
0x37c0b  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37c10  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass166_0::entityInfo
0x37c15  ldloc.s  0xA
0x37c17  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_LogicalName()
0x37c1c  callvirt instance void Microsoft.Crm.Metadata.EntityUpdateInfo::set_LogicalName(string value)
0x37c21  ldloc.s  4
0x37c23  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37c28  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass166_0::entityInfo
0x37c2d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x37c32  stloc.s  0xB
0x37c34  ldloc.s  0xB
0x37c36  ldloc.s  0xA
0x37c38  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::CreateDifferenceDescription(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag)
0x37c3d  stloc.s  0xC
0x37c3f  ldloc.s  7
0x37c41  ldarg.1
0x37c42  ldstr    aAttribute// "Attribute"
0x37c47  ldc.i4.1
0x37c48  newarr   [mscorlib]System.String
0x37c4d  dup
0x37c4e  ldc.i4.0
0x37c4f  ldstr    aAttributeid// "attributeid"
0x37c54  stelem.ref
0x37c55  ldloc.s  4
0x37c57  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37c5c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass166_0::context
0x37c61  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::CreateColumnsCollection(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x37c66  ldloc.s  4
0x37c68  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37c6d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass166_0::context
0x37c72  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x37c77  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.AttributeService::RetrievePrimaryKeyAttributeAsIfPublished(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x37c7c  stloc.s  0xD
0x37c7e  ldloc.s  4
0x37c80  ldloc.s  0xD
0x37c82  ldstr    aAttributeid// "attributeid"
0x37c87  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x37c8c  unbox.any [mscorlib]System.Guid
0x37c91  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass166_1::primaryKeyAttributeId
0x37c96  ldloc.s  4
0x37c98  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37c9d  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass166_0::entityInfo
0x37ca2  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_HasRelatedActivities()
0x37ca7  brfalse.s loc_37CC0
0x37ca9  ldarg.1
0x37caa  ldloc.s  4
0x37cac  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37cb1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass166_0::context
0x37cb6  call     bool Microsoft.Crm.Metadata.EntityService::HasRelatedActivities(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x37cbb  ldc.i4.0
0x37cbc  ceq
0x37cbe  br.s     loc_37CC1
0x37cc0  ldc.i4.0
0x37cc1  stloc.s  0xE
0x37cc3  ldloc.s  0xB
0x37cc5  ldstr    aIscollaboratio// "iscollaboration"
0x37cca  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x37ccf  brfalse.s loc_37CDA
0x37cd1  ldloc.s  0xB
0x37cd3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCollaboration()
0x37cd8  br.s     loc_37CDB
0x37cda  ldc.i4.0
0x37cdb  stloc.s  0xF
0x37cdd  ldloc.s  0xB
0x37cdf  ldstr    aAutocreateacce// "autocreateaccessteams"
0x37ce4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x37ce9  brfalse.s loc_37D00
0x37ceb  ldloc.s  0xB
0x37ced  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_AutoCreateAccessTeams()
0x37cf2  brfalse.s loc_37D00
0x37cf4  ldloc.s  0xA
0x37cf6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_AutoCreateAccessTeams()
0x37cfb  ldc.i4.0
0x37cfc  ceq
0x37cfe  br.s     loc_37D01
0x37d00  ldc.i4.0
0x37d01  stloc.s  0x10
0x37d03  ldloc.s  4
0x37d05  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37d0a  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass166_0::entityInfo
0x37d0f  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsActivityParty()
0x37d14  brfalse.s loc_37D22
0x37d16  ldloc.s  0xA
0x37d18  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsActivityParty()
0x37d1d  ldc.i4.0
0x37d1e  ceq
0x37d20  br.s     loc_37D23
0x37d22  ldc.i4.0
0x37d23  stloc.s  0x11
0x37d25  ldloc.s  0xB
0x37d27  ldstr    aAutocreateacce// "autocreateaccessteams"
0x37d2c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x37d31  brfalse.s loc_37D45
0x37d33  ldloc.s  0xB
0x37d35  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_AutoCreateAccessTeams()
0x37d3a  brtrue.s loc_37D45
0x37d3c  ldloc.s  0xA
0x37d3e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_AutoCreateAccessTeams()
0x37d43  br.s     loc_37D46
0x37d45  ldc.i4.0
0x37d46  stloc.s  0x12
0x37d48  ldloc.s  4
0x37d4a  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37d4f  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass166_0::entityInfo
0x37d54  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsBusinessProcessEnabled()
0x37d59  brfalse.s loc_37D67
0x37d5b  ldloc.s  0xA
0x37d5d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsBusinessProcessEnabled()
0x37d62  ldc.i4.0
0x37d63  ceq
0x37d65  br.s     loc_37D68
0x37d67  ldc.i4.0
0x37d68  stloc.s  0x13
0x37d6a  ldloc.s  4
0x37d6c  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37d71  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass166_0::entityInfo
0x37d76  callvirt instance bool Microsoft.Crm.Metadata.EntityUpdateInfo::get_IsSLAEnabled()
0x37d7b  brfalse.s loc_37D89
0x37d7d  ldloc.s  0xA
0x37d7f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsSLAEnabled()
0x37d84  ldc.i4.0
0x37d85  ceq
0x37d87  br.s     loc_37D8A
0x37d89  ldc.i4.0
0x37d8a  stloc.s  0x14
0x37d8c  ldloc.s  0xA
0x37d8e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_CanChangeTrackingBeEnabled()
0x37d93  pop
0x37d94  ldloc.s  5
0x37d96  ldloc.s  4
0x37d98  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37d9d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass166_0::context
0x37da2  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IsCustomizableCondition::IsEntityCustomizable(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x37da7  stloc.s  0x15
0x37da9  ldloc.s  5
0x37dab  ldloc.s  4
0x37dad  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37db2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass166_0::context
0x37db7  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CanModifyAdditionalSettingsCondition::CanModifyAdditionSettings(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.EntityFacade.IEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x37dbc  stloc.s  0x16
0x37dbe  ldloc.s  0xC
0x37dc0  ldnull
0x37dc1  cgt.un
0x37dc3  stloc.s  0x17
0x37dc5  ldarg.0
0x37dc6  ldloc.s  4
0x37dc8  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37dcd  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass166_0::entityInfo
0x37dd2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x37dd7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x37ddc  ldloc.s  4
0x37dde  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37de3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass166_0::context
0x37de8  call     instance bool Microsoft.Crm.Metadata.EntityService::IsFirstSystemConvertedUpgradeForNonSystemEntity(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x37ded  stloc.s  0x18
0x37def  ldloc.s  6
0x37df1  ldstr    aLogicalname// "logicalname"
0x37df6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x37dfb  castclass [mscorlib]System.String
0x37e00  stloc.s  0x19
0x37e02  ldloc.s  6
0x37e04  ldstr    aDataproviderid// "dataproviderid"
0x37e09  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x37e0e  brtrue.s loc_37E23
0x37e10  ldloc.s  6
0x37e12  ldstr    aDataproviderid// "dataproviderid"
0x37e17  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x37e1c  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x37e21  br.s     loc_37E2D
0x37e23  ldloca.s 0x1D
0x37e25  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x37e2b  ldloc.s  0x1D
0x37e2d  ldloc.s  4
0x37e2f  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
0x37e34  ldfld    class Microsoft.Crm.Metadata.EntityUpdateInfo <>c__DisplayClass166_0::entityInfo
0x37e39  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.EntityUpdateInfo::get_DataProviderId()
0x37e3e  stloc.s  0x1D
0x37e40  stloc.s  0x1E
0x37e42  ldloca.s 0x1D
0x37e44  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x37e49  ldloca.s 0x1E
0x37e4b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x37e50  beq.s    loc_37E55
0x37e52  ldc.i4.1
0x37e53  br.s     loc_37E74
0x37e55  ldloca.s 0x1D
0x37e57  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x37e5c  brtrue.s loc_37E61
0x37e5e  ldc.i4.0
0x37e5f  br.s     loc_37E74
0x37e61  ldloca.s 0x1D
0x37e63  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x37e68  ldloca.s 0x1E
0x37e6a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x37e6f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x37e74  brfalse  loc_37F85
0x37e79  ldloc.s  4
0x37e7b  ldfld    class <>c__DisplayClass166_0 <>c__DisplayClass166_1::CS$<>8__locals1
  ... truncated ...
```
