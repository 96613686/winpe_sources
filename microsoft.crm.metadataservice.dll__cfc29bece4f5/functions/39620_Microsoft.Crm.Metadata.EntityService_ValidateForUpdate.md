# Microsoft.Crm.Metadata.EntityService::ValidateForUpdate

- ea: `0x39620`
- end: `0x3993c`
- name: `Microsoft.Crm.Metadata.EntityService::ValidateForUpdate`
- size: `796`
- prototype: ``
- caller_count: `2`
- callee_count: `39`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x288f0`
- `0x37ad0`

## callees

- `0x36430`
- `0x367b0`
- `0x39620`
- `0x39940`
- `0x399d0`
- `0x39ad0`
- `0x39b90`
- `0x39c80`
- `0x39cc0`
- `0x39d60`
- `0x39dd0`
- `0x39ea0`
- `0x39fc0`
- `0x3a030`
- `0x3a0e0`
- `0x3a250`
- `0x3a3f0`
- `0x3a470`
- `0x3a4c0`
- `0x3a530`
- `0x3a630`
- `0x3a6c0`
- `0x3a7a0`
- `0x3a830`
- `0x3a880`
- `0x3a960`
- `0x3aa50`
- `0x3aad0`
- `0x3caf0`
- `0x3cc00`
- `0x3ce40`
- `0x3ce60`
- `0x3cf80`
- `0x3cfc0`
- `0x3d000`
- `0x3d7b0`
- `0x456b0`
- `0x565f0`
- `0x56710`

## string_xrefs

- `0x39625`: `isrenameable`

## pseudocode

```c

```

## disassembly

```asm
0x39620  ldarg.s  5
0x39622  brfalse.s loc_39651
0x39624  ldarg.2
0x39625  ldstr    aIsrenameable// "isrenameable"
0x3962a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3962f  unbox.any [mscorlib]System.Boolean
0x39634  brtrue.s loc_39651
0x39636  ldarg.0
0x39637  ldarg.2
0x39638  ldstr    aEntityid// "entityid"
0x3963d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x39642  unbox.any [mscorlib]System.Guid
0x39647  ldarg.s  6
0x39649  ldarg.1
0x3964a  ldarg.s  7
0x3964c  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateEntityRename(valuetype [mscorlib]System.Guid entityId, bool mergeLabels, class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x39651  ldarg.1
0x39652  callvirt instance string Microsoft.Crm.Metadata.EntityUpdateInfo::get_ExternalName()
0x39657  ldarg.s  7
0x39659  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3965e  ldarg.1
0x3965f  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.EntityUpdateInfo::get_DataProviderId()
0x39664  ldarg.1
0x39665  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.EntityUpdateInfo::get_DataSourceId()
0x3966a  ldarg.2
0x3966b  ldstr    aLogicalname// "logicalname"
0x39670  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x39675  castclass [mscorlib]System.String
0x3967a  call     void Microsoft.Crm.Metadata.EntityService::ValidateEntityExternalNameForUpdate(string entityExternalName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataProviderId, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> dataSourceId, string name)
0x3967f  ldarg.s  6
0x39681  brfalse.s loc_396A8
0x39683  ldarg.1
0x39684  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityUpdateInfo::get_NewDisplayName()
0x39689  brfalse.s loc_396A8
0x3968b  ldarg.1
0x3968c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityUpdateInfo::get_NewDisplayName()
0x39691  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::get_Count()
0x39696  brtrue.s loc_396A8
0x39698  ldstr    aDisplaynameMus// "DisplayName must not be empty collectio"...
0x3969d  ldc.i4   0x80040203
0x396a2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x396a7  throw
0x396a8  ldarg.s  6
0x396aa  brfalse.s loc_396D1
0x396ac  ldarg.1
0x396ad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityUpdateInfo::get_NewDisplayCollectionName()
0x396b2  brfalse.s loc_396D1
0x396b4  ldarg.1
0x396b5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityUpdateInfo::get_NewDisplayCollectionName()
0x396ba  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::get_Count()
0x396bf  brtrue.s loc_396D1
0x396c1  ldstr    aDisplaycollect_0// "DisplayCollectionName must not be empty"...
0x396c6  ldc.i4   0x80040203
0x396cb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x396d0  throw
0x396d1  ldarg.1
0x396d2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityUpdateInfo::get_NewDisplayName()
0x396d7  ldarg.1
0x396d8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x396dd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x396e2  ldstr    aLocalizedname// "LocalizedName"
0x396e7  ldc.i4.0
0x396e8  ldstr    aEntityDisplayN// "Entity Display Name"
0x396ed  ldarg.s  7
0x396ef  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x396f4  ldc.i4.0
0x396f5  call     void Microsoft.Crm.Metadata.LocalizedLabelHelper::ValidateLabelCollectionContents(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string parameterName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, [opt] bool throwIfCollectionIsNullOrEmpty)
0x396fa  ldarg.1
0x396fb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection Microsoft.Crm.Metadata.EntityUpdateInfo::get_NewDisplayCollectionName()
0x39700  ldarg.1
0x39701  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x39706  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x3970b  ldstr    aLocalizedcolle// "LocalizedCollectionName"
0x39710  ldc.i4.0
0x39711  ldstr    aEntityDisplayC// "Entity Display Collection Name"
0x39716  ldarg.s  7
0x39718  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3971d  ldc.i4.0
0x3971e  call     void Microsoft.Crm.Metadata.LocalizedLabelHelper::ValidateLabelCollectionContents(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection labelCollection, valuetype [mscorlib]System.Guid objectId, string objectColumnName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode, string parameterName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, [opt] bool throwIfCollectionIsNullOrEmpty)
0x39723  ldarg.2
0x39724  ldstr    aIscustomentity// "iscustomentity"
0x39729  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x3972e  brtrue.s loc_39742
0x39730  ldarg.2
0x39731  ldstr    aIscustomentity// "iscustomentity"
0x39736  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3973b  unbox.any [mscorlib]System.Boolean
0x39740  br.s     loc_39743
0x39742  ldc.i4.0
0x39743  stloc.0
0x39744  ldloc.0
0x39745  brtrue   loc_397E5
0x3974a  ldarg.0
0x3974b  ldarg.1
0x3974c  ldarg.2
0x3974d  call     instance bool Microsoft.Crm.Metadata.EntityService::IsAvailableOfflinePropertyModified(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData)
0x39752  brtrue.s loc_39766
0x39754  ldarg.1
0x39755  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x3975a  ldstr    aIsreplicationu// "isreplicationuserfiltered"
0x3975f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x39764  brfalse.s loc_39799
0x39766  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3976b  ldstr    aEntity0IsNotAC_0// "Entity {0} is not a custom entity and t"...
0x39770  ldc.i4.1
0x39771  newarr   [mscorlib]System.Object
0x39776  dup
0x39777  ldc.i4.0
0x39778  ldarg.2
0x39779  ldstr    aEntityid// "entityid"
0x3977e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x39783  unbox.any [mscorlib]System.Guid
0x39788  box      [mscorlib]System.Guid
0x3978d  stelem.ref
0x3978e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x39793  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x39798  throw
0x39799  ldarg.0
0x3979a  ldarg.1
0x3979b  ldarg.2
0x3979c  call     instance bool Microsoft.Crm.Metadata.EntityService::IsMailMergeEnabledPropertyModified(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData)
0x397a1  brfalse.s loc_397D6
0x397a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x397a8  ldstr    aEntity0IsNotAC_1// "Entity {0} is not a custom entity and t"...
0x397ad  ldc.i4.1
0x397ae  newarr   [mscorlib]System.Object
0x397b3  dup
0x397b4  ldc.i4.0
0x397b5  ldarg.2
0x397b6  ldstr    aEntityid// "entityid"
0x397bb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x397c0  unbox.any [mscorlib]System.Guid
0x397c5  box      [mscorlib]System.Guid
0x397ca  stelem.ref
0x397cb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x397d0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x397d5  throw
0x397d6  ldarg.0
0x397d7  ldarg.1
0x397d8  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateIconsAreNotPresent(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo)
0x397dd  ldarg.0
0x397de  ldarg.1
0x397df  ldarg.2
0x397e0  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateEntitySetNameIsPresent(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData)
0x397e5  ldarg.0
0x397e6  ldarg.1
0x397e7  ldarg.2
0x397e8  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateVirtualEntityUpdate(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData)
0x397ed  ldarg.1
0x397ee  callvirt instance string Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityColor()
0x397f3  call     void Microsoft.Crm.Metadata.EntityService::ValidateEntityColor(string entityColor)
0x397f8  ldarg.0
0x397f9  ldarg.1
0x397fa  ldarg.2
0x397fb  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateOneNoteIntegrationEnabledSettings(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData)
0x39800  ldarg.0
0x39801  ldarg.1
0x39802  ldarg.2
0x39803  ldarg.s  7
0x39805  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateDocumentRecommendationEnabledSettingsForUpdate(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3980a  ldarg.0
0x3980b  ldarg.1
0x3980c  ldarg.2
0x3980d  ldloc.0
0x3980e  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateBusinessProcessEnabledSetting(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData, bool isCustomEntity)
0x39813  ldarg.s  7
0x39815  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ObjectServiceUtility::IsSLAFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3981a  brfalse.s loc_39824
0x3981c  ldarg.0
0x3981d  ldarg.1
0x3981e  ldarg.2
0x3981f  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateSLAEnabledSetting(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData)
0x39824  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x39829  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x3982e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x39833  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x39838  ldarg.s  7
0x3983a  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3983f  brfalse.s loc_39849
0x39841  ldarg.0
0x39842  ldarg.1
0x39843  ldarg.2
0x39844  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateExternalAppSetting(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData)
0x39849  ldarg.0
0x3984a  ldarg.1
0x3984b  ldarg.2
0x3984c  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateQueueSetting(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData)
0x39851  ldarg.0
0x39852  ldarg.1
0x39853  ldarg.2
0x39854  ldarg.3
0x39855  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateConnectionSetting(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity primaryFieldAttribute)
0x3985a  ldarg.0
0x3985b  ldarg.1
0x3985c  ldarg.3
0x3985d  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateFeedbackSetting(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity primaryFieldAttribute)
0x39862  ldarg.0
0x39863  ldarg.1
0x39864  ldarg.2
0x39865  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateAutoRouteSettings(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData)
0x3986a  ldarg.0
0x3986b  ldarg.1
0x3986c  ldarg.2
0x3986d  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateActivityPartySetting(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData)
0x39872  ldarg.0
0x39873  ldarg.1
0x39874  ldarg.2
0x39875  ldloc.0
0x39876  ldarg.s  7
0x39878  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateQuickCreateForUpdateEntity(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData, bool isCustomEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3987d  ldarg.s  4
0x3987f  brfalse.s loc_398AC
0x39881  ldarg.s  7
0x39883  newobj   instance void Microsoft.Crm.Metadata.EntityPropertiesBackCompatOverrider::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x39888  ldarg.1
0x39889  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x3988e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x39893  stloc.1
0x39894  ldloca.s 1
0x39896  ldstr    aN// "N"
0x3989b  call     instance string [mscorlib]System.Guid::ToString(string)
0x398a0  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x398a5  call     instance bool Microsoft.Crm.Metadata.EntityPropertiesBackCompatOverrider::ShouldValidateChangeTrackingSettings(string entityId)
0x398aa  brfalse.s loc_398B6
0x398ac  ldarg.0
0x398ad  ldarg.1
0x398ae  ldarg.2
0x398af  ldarg.s  7
0x398b1  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateChangeTrackingSettingsForUpdateEntity(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x398b6  ldarg.0
0x398b7  ldarg.1
0x398b8  ldarg.2
0x398b9  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateDaysSinceRecordLastModifiedForUpdateEntity(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData)
0x398be  ldarg.0
0x398bf  ldarg.1
0x398c0  ldarg.2
0x398c1  ldarg.s  7
0x398c3  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateEntityLinkedToMobileOfflineProfileItem(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x398c8  ldarg.0
0x398c9  ldarg.1
0x398ca  ldarg.2
0x398cb  ldarg.s  7
0x398cd  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateMocaEnabledFlagForUpdateEntity(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x398d2  ldarg.0
0x398d3  ldarg.1
0x398d4  ldarg.2
0x398d5  ldarg.s  7
0x398d7  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateMobileOfflineFlagsForBPFEntity(class Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x398dc  ldloc.0
0x398dd  brfalse.s loc_398EF
0x398df  ldarg.s  4
0x398e1  brtrue.s loc_398EF
0x398e3  ldarg.0
0x398e4  ldarg.1
0x398e5  callvirt instance string Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntitySetName()
0x398ea  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateEntitySetNameIsCompliant(string entitySetName)
0x398ef  ldarg.1
0x398f0  callvirt instance string Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntitySetName()
0x398f5  brfalse.s loc_39927
0x398f7  ldarg.1
0x398f8  callvirt instance string Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntitySetName()
0x398fd  ldarg.2
0x398fe  ldstr    aEntitysetname// "entitysetname"
0x39903  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x39908  castclass [mscorlib]System.String
0x3990d  call     bool [mscorlib]System.String::Equals(string, string)
0x39912  brtrue.s loc_39927
0x39914  ldarg.0
0x39915  ldarg.1
0x39916  callvirt instance string Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntitySetName()
0x3991b  ldarg.s  7
0x3991d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x39922  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateEntitySetNameIsUnique(string entitySetName, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x39927  ldarg.0
0x39928  ldarg.1
0x39929  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntityDescription()
0x3992e  ldarg.2
0x3992f  ldarg.s  7
0x39931  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x39936  call     instance void Microsoft.Crm.Metadata.EntityService::ValidateExternalSearchSettingsForUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag newEntityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity oldEntityInfo, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x3993b  ret
```
