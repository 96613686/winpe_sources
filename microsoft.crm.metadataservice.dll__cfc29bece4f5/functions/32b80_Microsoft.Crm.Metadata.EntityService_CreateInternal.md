# Microsoft.Crm.Metadata.EntityService::CreateInternal

- ea: `0x32b80`
- end: `0x32e40`
- name: `Microsoft.Crm.Metadata.EntityService::CreateInternal`
- size: `704`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x306d0`

## callees

- `0x2cab0`
- `0x2cb50`
- `0x2cbe0`
- `0x2cd30`
- `0x2cd70`
- `0x2cdb0`
- `0x2ce50`
- `0x2d290`
- `0x2d430`
- `0x2d4d0`
- `0x2d530`
- `0x310b0`
- `0x32b80`
- `0x32e40`
- `0x32ef0`
- `0x32f30`
- `0x33370`
- `0x33400`
- `0x33450`
- `0x334b0`
- `0x34c90`
- `0x357d0`
- `0x35870`
- `0x359c0`
- `0x36bb0`
- `0x37700`
- `0x38960`
- `0x38a90`
- `0x38bc0`
- `0x4d140`
- `0x4edf0`
- `0x565f0`
- `0x56760`
- `0x57120`
- `0x59870`
- `0x5aa70`
- `0x5db70`
- `0x61ca0`
- `0x61f80`
- `0x64fb0`
- `0x69510`
- `0x69740`

## string_xrefs

- `0x32cf1`: `Create`
- `0x32d24`: `Update`
- `0x32d35`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x32b80  ldarg.1
0x32b81  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x32b86  stloc.0
0x32b87  ldarg.0
0x32b88  ldarg.1
0x32b89  call     instance void Microsoft.Crm.Metadata.EntityService::InitializeDefaultsForVirtualEntity(class Microsoft.Crm.Metadata.EntityCreateInfo entityCreateData)
0x32b8e  ldarg.0
0x32b8f  ldarg.1
0x32b90  ldarg.2
0x32b91  ldarg.3
0x32b92  callvirt instance void Microsoft.Crm.Metadata.EntityService::ValidateForCreate(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32b97  ldarg.0
0x32b98  ldarg.1
0x32b99  ldarg.2
0x32b9a  ldarg.3
0x32b9b  call     instance void Microsoft.Crm.Metadata.EntityService::SetOriginalEntityLabels(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32ba0  ldarg.0
0x32ba1  ldarg.1
0x32ba2  ldarg.2
0x32ba3  ldarg.3
0x32ba4  call     instance void Microsoft.Crm.Metadata.EntityService::SetObjectTypeCode(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper helper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32ba9  ldloc.0
0x32baa  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCustomEntity()
0x32baf  brtrue.s loc_32BB9
0x32bb1  ldloc.0
0x32bb2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCustomizable()
0x32bb7  brfalse.s loc_32BC8
0x32bb9  ldloc.0
0x32bba  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_CanCreateAttributes()
0x32bbf  brfalse.s loc_32BC8
0x32bc1  ldloc.0
0x32bc2  ldc.i4.1
0x32bc3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::set_CanBeSecured(bool)
0x32bc8  ldarg.1
0x32bc9  callvirt instance valuetype Microsoft.Crm.Metadata.SuppressMetadataOperationTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_SuppressMetadataOperationType()
0x32bce  ldc.i4.s 0x10
0x32bd0  and
0x32bd1  brtrue.s loc_32BDA
0x32bd3  ldarg.1
0x32bd4  ldarg.3
0x32bd5  call     void Microsoft.Crm.Metadata.SecurityHelper::CreateEntityHelper(class Microsoft.Crm.Metadata.EntityCreateInfo entityCreateInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32bda  ldarg.0
0x32bdb  ldarg.1
0x32bdc  ldarg.3
0x32bdd  ldarg.2
0x32bde  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x32be3  call     instance void Microsoft.Crm.Metadata.EntityService::CreateUIData(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isInternalSolutionContext)
0x32be8  ldarg.0
0x32be9  ldarg.1
0x32bea  ldarg.2
0x32beb  ldarg.3
0x32bec  callvirt instance void Microsoft.Crm.Metadata.EntityService::CreateDefaultEntityData(class Microsoft.Crm.Metadata.IEntityInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32bf1  ldarg.1
0x32bf2  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsBPFEntity()
0x32bf7  brfalse.s loc_32C02
0x32bf9  ldarg.0
0x32bfa  ldarg.1
0x32bfb  ldarg.2
0x32bfc  ldarg.3
0x32bfd  call     instance void Microsoft.Crm.Metadata.EntityService::CreateBpfEntityAttributes(class Microsoft.Crm.Metadata.IEntityInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32c02  ldarg.1
0x32c03  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.EntityCreateInfo::get_DataProviderId()
0x32c08  stloc.2
0x32c09  ldloca.s 2
0x32c0b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x32c10  brfalse.s loc_32C29
0x32c12  ldarg.1
0x32c13  ldarg.2
0x32c14  ldarg.3
0x32c15  ldloc.0
0x32c16  ldarg.3
0x32c17  ldarg.1
0x32c18  callvirt instance string Microsoft.Crm.Metadata.EntityCreateInfo::get_LogicalName()
0x32c1d  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Metadata.EntityService::GetActivitiesList(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string entityName)
0x32c22  call     void Microsoft.Crm.Metadata.VirtualEntityRelationshipHelper::CreateRelationshipWithEntity(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag entityDescription, class [mscorlib]System.Collections.Generic.List`1<string> activities)
0x32c27  br.s     loc_32C33
0x32c29  ldarg.0
0x32c2a  ldarg.1
0x32c2b  ldarg.2
0x32c2c  ldarg.3
0x32c2d  ldloc.0
0x32c2e  call     instance void Microsoft.Crm.Metadata.EntityService::CreateRelationshipWithEntity(class Microsoft.Crm.Metadata.IEntityInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag entityDescription)
0x32c33  ldarg.1
0x32c34  ldarg.2
0x32c35  ldarg.3
0x32c36  call     void Microsoft.Crm.Metadata.EntityService::ProcessAttributeList(class Microsoft.Crm.Metadata.IEntityInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32c3b  ldarg.2
0x32c3c  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x32c41  ldarg.1
0x32c42  ldarg.3
0x32c43  ldarg.2
0x32c44  call     void Microsoft.Crm.Metadata.AppCommon.AppCommonService::PostCreateEntity(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x32c49  ldarg.2
0x32c4a  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x32c4f  ldarg.1
0x32c50  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsBPFEntity()
0x32c55  brtrue.s loc_32C5F
0x32c57  ldarg.0
0x32c58  ldarg.1
0x32c59  ldarg.3
0x32c5a  call     instance void Microsoft.Crm.Metadata.EntityService::UpdateViews(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32c5f  ldarg.1
0x32c60  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsBusinessProcessEnabled()
0x32c65  brfalse.s loc_32C88
0x32c67  ldloc.0
0x32c68  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsActivity()
0x32c6d  brfalse.s loc_32C88
0x32c6f  ldarg.1
0x32c70  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.EntityCreateInfo::get_DataProviderId()
0x32c75  stloc.2
0x32c76  ldloca.s 2
0x32c78  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x32c7d  brtrue.s loc_32C88
0x32c7f  ldarg.0
0x32c80  ldloc.0
0x32c81  ldarg.2
0x32c82  ldarg.3
0x32c83  call     instance void Microsoft.Crm.Metadata.EntityService::CreateBusinessProcessRelationship(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag entityDescription, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32c88  ldarg.1
0x32c89  callvirt instance valuetype Microsoft.Crm.Metadata.SuppressMetadataOperationTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_SuppressMetadataOperationType()
0x32c8e  ldc.i4.1
0x32c8f  and
0x32c90  brtrue.s loc_32C9F
0x32c92  ldarg.0
0x32c93  ldloc.0
0x32c94  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_ObjectTypeCode()
0x32c99  ldarg.3
0x32c9a  call     instance void Microsoft.Crm.Metadata.EntityService::PublishUIData(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32c9f  ldarg.1
0x32ca0  ldarg.1
0x32ca1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityCreateInfo::get_DisplayCollectionName()
0x32ca6  ldarg.3
0x32ca7  call     void Microsoft.Crm.Metadata.EntityService::CreateReplication(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection displayCollectionName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32cac  ldloc.0
0x32cad  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_LogicalName()
0x32cb2  ldarg.1
0x32cb3  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Metadata.EntityCreateInfo::get_DisplayAreas()
0x32cb8  ldarg.3
0x32cb9  ldc.i4.0
0x32cba  ldarg.1
0x32cbb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityCreateInfo::get_SiteMapId()
0x32cc0  ldarg.1
0x32cc1  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsBPFEntity()
0x32cc6  call     void Microsoft.Crm.Metadata.SiteMapHelper::UpdateSiteMap(string logicalName, class [mscorlib]System.Collections.IDictionary displayAreas, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool validateDependencies, valuetype [mscorlib]System.Guid siteMapId, [opt] bool isBPFEntity)
0x32ccb  newobj   instance void Microsoft.Crm.MetadataService.SdkMessageFilterHelper::.ctor()
0x32cd0  stloc.1
0x32cd1  ldloc.0
0x32cd2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsCustomEntity()
0x32cd7  brfalse  loc_32D71
0x32cdc  ldarg.1
0x32cdd  callvirt instance valuetype Microsoft.Crm.Metadata.SuppressMetadataOperationTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_SuppressMetadataOperationType()
0x32ce2  ldc.i4.s 0x20
0x32ce4  and
0x32ce5  brtrue   loc_32D71
0x32cea  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x32cef  stloc.3
0x32cf0  ldloc.3
0x32cf1  ldstr    aCreate// "Create"
0x32cf6  ldloc.0
0x32cf7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_AvailableForCreate()
0x32cfc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x32d01  ldloc.3
0x32d02  ldstr    aRetrieve// "Retrieve"
0x32d07  ldloc.0
0x32d08  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_AvailableForRetrieve()
0x32d0d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x32d12  ldloc.3
0x32d13  ldstr    aRetrievemultip// "RetrieveMultiple"
0x32d18  ldloc.0
0x32d19  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_AvailableForRetrieveMultiple()
0x32d1e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x32d23  ldloc.3
0x32d24  ldstr    aUpdate// "Update"
0x32d29  ldloc.0
0x32d2a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_AvailableForUpdate()
0x32d2f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x32d34  ldloc.3
0x32d35  ldstr    aDelete// "Delete"
0x32d3a  ldloc.0
0x32d3b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_AvailableForDelete()
0x32d40  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x32d45  ldloc.1
0x32d46  ldloc.0
0x32d47  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsBPFEntity()
0x32d4c  ldloc.0
0x32d4d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_IsReplicated()
0x32d52  ldloc.0
0x32d53  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_ObjectTypeCode()
0x32d58  ldarg.1
0x32d59  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsCustomActivity()
0x32d5e  ldloc.0
0x32d5f  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_DataProviderId()
0x32d64  ldloc.0
0x32d65  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_OwnershipTypeMask()
0x32d6a  ldarg.3
0x32d6b  ldloc.3
0x32d6c  callvirt instance void Microsoft.Crm.MetadataService.SdkMessageFilterHelper::CreateSdkFiltersForCustomEntity(bool isBPFEntity, bool isReplicated, int32 objectTypeCode, bool isCustomActivity, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataProviderId, int32 ownershipTypeMask, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> sdkFilterRestrictionLevels)
0x32d71  ldarg.1
0x32d72  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsEnabledForExternalChannels()
0x32d77  brfalse.s loc_32DF6
0x32d79  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x32d7e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x32d83  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x32d88  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x32d8d  ldarg.3
0x32d8e  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x32d93  brtrue.s loc_32D9D
0x32d95  ldarg.2
0x32d96  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x32d9b  brfalse.s loc_32DF6
0x32d9d  newobj   instance void Microsoft.Crm.Metadata.RelationshipService::.ctor()
0x32da2  stloc.s  4
0x32da4  ldloc.0
0x32da5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_Name()
0x32daa  ldarg.3
0x32dab  call     class Microsoft.Crm.Metadata.RelationshipCreateInfo Microsoft.Crm.Metadata.EntityService::GetCreatedByRelationshipCreateInfo(string entityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32db0  stloc.s  5
0x32db2  ldloc.s  5
0x32db4  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x32db9  ldarg.3
0x32dba  call     bool Microsoft.Crm.Metadata.EntityService::CheckIfRelationshipExists(string name, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32dbf  brtrue.s loc_32DCD
0x32dc1  ldloc.s  4
0x32dc3  ldloc.s  5
0x32dc5  ldarg.3
0x32dc6  ldarg.2
0x32dc7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipServiceBase::CreateInternal(class Microsoft.Crm.Metadata.IRelationshipCreateInfo relationshipInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x32dcc  pop
0x32dcd  ldloc.0
0x32dce  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_Name()
0x32dd3  ldarg.3
0x32dd4  call     class Microsoft.Crm.Metadata.RelationshipCreateInfo Microsoft.Crm.Metadata.EntityService::GetUpdatedByRelationshipCreateInfo(string entityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32dd9  stloc.s  6
0x32ddb  ldloc.s  6
0x32ddd  callvirt instance string Microsoft.Crm.Metadata.RelationshipCreateInfo::get_SchemaName()
0x32de2  ldarg.3
0x32de3  call     bool Microsoft.Crm.Metadata.EntityService::CheckIfRelationshipExists(string name, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32de8  brtrue.s loc_32DF6
0x32dea  ldloc.s  4
0x32dec  ldloc.s  6
0x32dee  ldarg.3
0x32def  ldarg.2
0x32df0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.RelationshipServiceBase::CreateInternal(class Microsoft.Crm.Metadata.IRelationshipCreateInfo relationshipInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x32df5  pop
0x32df6  newobj   instance void Microsoft.Crm.Metadata.CrmCommon.CrmCommonService::.ctor()
0x32dfb  ldarg.1
0x32dfc  ldarg.3
0x32dfd  ldarg.2
0x32dfe  callvirt instance void Microsoft.Crm.Metadata.CrmCommon.CrmCommonService::PostCreateEntity(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper)
0x32e03  ldarg.3
0x32e04  newobj   instance void Microsoft.Crm.Metadata.EntityPropertiesBackCompatOverrider::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x32e09  ldarg.1
0x32e0a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x32e0f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag::get_InnerEntityData()
0x32e14  ldarg.1
0x32e15  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x32e1a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x32e1f  stloc.s  7
0x32e21  ldloca.s 7
0x32e23  constrained. [mscorlib]System.Guid
0x32e29  callvirt instance string [mscorlib]System.Object::ToString()
0x32e2e  callvirt instance void Microsoft.Crm.Metadata.EntityPropertiesBackCompatOverrider::EntityOverride(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, string entityId)
0x32e33  ldarg.2
0x32e34  callvirt instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ProcessQueue()
0x32e39  ldloc.0
0x32e3a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x32e3f  ret
```
