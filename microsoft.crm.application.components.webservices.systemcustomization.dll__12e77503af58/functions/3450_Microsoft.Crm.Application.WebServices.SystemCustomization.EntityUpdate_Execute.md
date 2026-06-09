# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::Execute

- ea: `0x3450`
- end: `0x379b`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::Execute`
- size: `843`
- prototype: ``
- caller_count: `3`
- callee_count: `35`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x5ea0`
- `0xada0`
- `0xb050`

## callees

- `0x190`
- `0x1a0`
- `0x200`
- `0x270`
- `0x2b0`
- `0x330`
- `0x2b10`
- `0x3450`
- `0x3920`
- `0x39a0`
- `0x39c0`
- `0x3a00`
- `0x3a40`
- `0x3a60`
- `0x3a80`
- `0x3ac0`
- `0x3c10`
- `0x3c90`
- `0x3cb0`
- `0x3cd0`
- `0x3d20`
- `0x3d60`
- `0x3da0`
- `0x3dc0`
- `0x3de0`
- `0x3e00`
- `0x3e20`
- `0x3e40`
- `0x3eb0`
- `0x3f20`
- `0x3f80`
- `0x3ff0`
- `0x4100`
- `0x4120`
- `0x4230`

## string_xrefs

- `0x3600`: `readonlyinmobileclient`
- `0x360e`: `readonlyinmobileclient`
- `0x36f7`: `readingpaneenabled`
- `0x3705`: `readingpaneenabled`
- `0x3698`: `<fetch version="1.0" output-format="xml-platform" mapping="logical" distinct="false"><entity name="{0}"><filter type="and"><condition attribute="modifiedon" operator="last-x-days" value="{1}"/></filter></entity></fetch>`

## pseudocode

```c

```

## disassembly

```asm
0x3450  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::CheckPrivileges()
0x3455  ldarg.1
0x3456  ldstr    aEntityid// "entityid"
0x345b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x3460  stloc.0
0x3461  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3466  stloc.1
0x3467  ldloc.1
0x3468  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x346d  ldloc.0
0x346e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x3473  stloc.2
0x3474  ldloc.0
0x3475  ldloc.1
0x3476  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::.ctor(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x347b  stloc.3
0x347c  ldloc.3
0x347d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::InitializeLabelCollections()
0x3482  ldloc.3
0x3483  ldloc.2
0x3484  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::SetDefaultValue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0x3489  ldloc.3
0x348a  ldarg.1
0x348b  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetSchemaParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3490  ldloc.3
0x3491  ldarg.1
0x3492  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetEntityColor(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag parameterBag)
0x3497  ldloc.3
0x3498  ldarg.1
0x3499  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetEntityHelpParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag parameterBag)
0x349e  ldloc.2
0x349f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x34a4  brfalse.s loc_34B1
0x34a6  ldloc.2
0x34a7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x34ac  ldc.i4.0
0x34ad  ceq
0x34af  br.s     loc_34B2
0x34b1  ldc.i4.0
0x34b2  dup
0x34b3  brfalse.s loc_34BC
0x34b5  ldloc.3
0x34b6  ldarg.1
0x34b7  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetMailMergeParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x34bc  ldloc.3
0x34bd  ldarg.1
0x34be  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::LogRetrieveAuditChanges(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x34c3  ldloc.2
0x34c4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0x34c9  brfalse.s loc_34EE
0x34cb  ldloc.3
0x34cc  ldarg.1
0x34cd  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetDuplicateDetectionParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x34d2  ldloc.3
0x34d3  ldarg.1
0x34d4  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetAuditParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x34d9  ldloc.3
0x34da  ldarg.1
0x34db  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetChangeTrackingParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x34e0  ldloc.3
0x34e1  ldarg.1
0x34e2  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetCollaborationParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x34e7  ldloc.3
0x34e8  ldarg.1
0x34e9  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetQuickCreateParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x34ee  ldloc.3
0x34ef  ldarg.1
0x34f0  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetDocumentManagementParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x34f5  ldloc.3
0x34f6  ldarg.1
0x34f7  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetVirtualEntityParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x34fc  ldloc.3
0x34fd  ldarg.1
0x34fe  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetExternalNameParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3503  ldloc.3
0x3504  ldarg.1
0x3505  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetExternalCollectionNameParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x350a  ldloc.3
0x350b  ldarg.1
0x350c  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetOneNoteIntegrationParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3511  ldloc.3
0x3512  ldarg.1
0x3513  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetKnowledgeManagementParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3518  ldloc.3
0x3519  ldarg.1
0x351a  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetDocumentRecommendationParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x351f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3524  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSLAFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3529  brfalse.s loc_3532
0x352b  ldloc.3
0x352c  ldarg.1
0x352d  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetSlaParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3532  ldloc.3
0x3533  ldarg.1
0x3534  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetAutoCreateAccessTeamsParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3539  ldloc.3
0x353a  ldloc.2
0x353b  ldarg.1
0x353c  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetActivityPartyParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMD, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3541  ldloc.3
0x3542  ldloc.2
0x3543  ldarg.1
0x3544  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetBusinessProcessParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMD, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3549  brfalse.s loc_357D
0x354b  ldloc.3
0x354c  ldarg.1
0x354d  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetRichClientParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3552  ldloc.3
0x3553  ldloc.2
0x3554  ldarg.1
0x3555  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetAssociatedEntityParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMD, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x355a  ldarg.1
0x355b  ldstr    aDisplayareas// "displayareas"
0x3560  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3565  brfalse.s loc_357D
0x3567  ldloc.3
0x3568  ldarg.1
0x3569  ldstr    aDisplayareas// "displayareas"
0x356e  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x3573  call     class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::GetDisplayAreaParams(class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3578  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_NewDisplayAreas(class [mscorlib]System.Collections.IDictionary)
0x357d  ldarg.1
0x357e  ldstr    aSitemapid// "sitemapid"
0x3583  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3588  brfalse.s loc_359B
0x358a  ldloc.3
0x358b  ldarg.1
0x358c  ldstr    aSitemapid// "sitemapid"
0x3591  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid(string name)
0x3596  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_SiteMapId(valuetype [mscorlib]System.Guid)
0x359b  ldloc.3
0x359c  ldloc.2
0x359d  ldarg.1
0x359e  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetAssociatedFeedbackParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMD, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x35a3  ldloc.3
0x35a4  ldloc.2
0x35a5  ldarg.1
0x35a6  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetConnectionsParams(class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo entityInfo, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMD, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x35ab  ldloc.2
0x35ac  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MobileAccessLevels [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_MobileAccessLevelMask()
0x35b1  brfalse.s loc_35D1
0x35b3  ldarg.1
0x35b4  ldstr    aVisibleinmobil// "visibleinmobile"
0x35b9  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x35be  brfalse.s loc_35D1
0x35c0  ldloc.3
0x35c1  ldarg.1
0x35c2  ldstr    aVisibleinmobil// "visibleinmobile"
0x35c7  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x35cc  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsVisibleInMobile(bool)
0x35d1  ldloc.2
0x35d2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyMobileClientVisibility()
0x35d7  brfalse.s loc_35F7
0x35d9  ldarg.1
0x35da  ldstr    aVisibleinmobil_0// "visibleinmobileclient"
0x35df  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x35e4  brfalse.s loc_35F7
0x35e6  ldloc.3
0x35e7  ldarg.1
0x35e8  ldstr    aVisibleinmobil_0// "visibleinmobileclient"
0x35ed  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x35f2  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsVisibleInMobileClient(bool)
0x35f7  ldloc.2
0x35f8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyMobileClientReadOnly()
0x35fd  brfalse.s loc_361D
0x35ff  ldarg.1
0x3600  ldstr    aReadonlyinmobi// "readonlyinmobileclient"
0x3605  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x360a  brfalse.s loc_361D
0x360c  ldloc.3
0x360d  ldarg.1
0x360e  ldstr    aReadonlyinmobi// "readonlyinmobileclient"
0x3613  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3618  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsReadOnlyInMobileClient(bool)
0x361d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3622  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsMocaOfflineFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3627  brfalse  loc_36F6
0x362c  ldloc.2
0x362d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanModifyMobileClientOffline()
0x3632  brfalse  loc_36F6
0x3637  ldarg.1
0x3638  ldstr    aOfflineinmobil// "offlineinmobileclient"
0x363d  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3642  brfalse.s loc_3655
0x3644  ldloc.3
0x3645  ldarg.1
0x3646  ldstr    aOfflineinmobil// "offlineinmobileclient"
0x364b  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3650  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsOfflineInMobileClient(bool)
0x3655  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x365a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsMocaOfflineOrgFilterFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x365f  stloc.s  4
0x3661  ldarg.1
0x3662  ldstr    aDayssincerecor// "dayssincerecordlastmodified"
0x3667  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x366c  brfalse.s loc_36CF
0x366e  ldloc.3
0x366f  ldarg.1
0x3670  ldstr    aDayssincerecor// "dayssincerecordlastmodified"
0x3675  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x367a  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_DaysSinceRecordLastModified(int32)
0x367f  ldloc.s  4
0x3681  brtrue.s loc_36CF
0x3683  ldloc.2
0x3684  brfalse.s loc_36CF
0x3686  ldloc.2
0x3687  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x368c  ldstr    aModifiedon// "modifiedon"
0x3691  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x3696  brfalse.s loc_36C4
0x3698  ldstr    aFetchVersion10// "<fetch version=\"1.0\" output-format=\""...
0x369d  stloc.s  5
0x369f  ldloc.3
0x36a0  ldloc.s  5
0x36a2  ldloc.2
0x36a3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x36a8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlAttributeEncode(string)
0x36ad  ldloc.3
0x36ae  callvirt instance int32 [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::get_DaysSinceRecordLastModified()
0x36b3  box      [mscorlib]System.Int32
0x36b8  call     string [mscorlib]System.String::Format(string, object, object)
0x36bd  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_MobileOfflineFilters(string)
0x36c2  br.s     loc_36CF
0x36c4  ldloc.3
0x36c5  ldsfld   string [mscorlib]System.String::Empty
0x36ca  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_MobileOfflineFilters(string)
0x36cf  ldloc.s  4
0x36d1  brfalse.s loc_36F6
0x36d3  ldarg.1
0x36d4  ldstr    aMobileofflinef// "mobileofflinefilters"
0x36d9  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x36de  brfalse.s loc_36F6
0x36e0  ldloc.3
0x36e1  ldarg.1
0x36e2  ldstr    aMobileofflinef// "mobileofflinefilters"
0x36e7  ldsfld   string [mscorlib]System.String::Empty
0x36ec  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x36f1  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_MobileOfflineFilters(string)
0x36f6  ldarg.1
0x36f7  ldstr    aReadingpaneena// "readingpaneenabled"
0x36fc  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3701  brfalse.s loc_3714
0x3703  ldloc.3
0x3704  ldarg.1
0x3705  ldstr    aReadingpaneena// "readingpaneenabled"
0x370a  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x370f  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsReadingPaneEnabled(bool)
0x3714  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x3719  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x371e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x3723  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x3728  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x372d  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3732  brfalse.s loc_3752
0x3734  ldarg.1
0x3735  ldstr    aIsenabledforex// "isenabledforexternalchannels"
0x373a  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x373f  brfalse.s loc_3752
0x3741  ldloc.3
0x3742  ldarg.1
0x3743  ldstr    aIsenabledforex// "isenabledforexternalchannels"
0x3748  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x374d  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsEnabledForExternalChannels(bool)
0x3752  ldloc.2
0x3753  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityService [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityServiceFactory::CreateEntityService(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0x3758  ldloc.0
0x3759  ldloc.3
0x375a  ldc.i4.1
0x375b  ldarg.0
0x375c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3761  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3766  brtrue.s loc_376B
0x3768  ldarg.0
0x3769  br.s     loc_3770
0x376b  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::DefaultSolutionId
0x3770  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityService::Update(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo, bool, valuetype [mscorlib]System.Guid)
0x3775  ldarg.0
0x3776  ldloc.2
0x3777  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x377c  ldarg.1
0x377d  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::UpdatePrimaryImage(valuetype [mscorlib]System.Guid solutionId, valuetype [mscorlib]System.Guid entityId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x3782  ldloc.2
0x3783  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0x3788  brfalse.s loc_379A
0x378a  ldloc.2
0x378b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x3790  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3795  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::FlushMetadataCache(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x379a  ret
```
