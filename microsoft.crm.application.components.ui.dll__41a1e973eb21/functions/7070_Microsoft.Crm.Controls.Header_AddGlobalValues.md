# Microsoft.Crm.Controls.Header::AddGlobalValues

- ea: `0x7070`
- end: `0x75d2`
- name: `Microsoft.Crm.Controls.Header::AddGlobalValues`
- size: `1378`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1df0`
- `0x7a90`

## callees

- `0x2ef0`
- `0x2f00`
- `0x2f20`
- `0x2fe0`
- `0x30a0`
- `0x38d0`
- `0x6e40`
- `0x7070`
- `0x75e0`
- `0x7680`
- `0x7720`
- `0x7860`
- `0x7920`
- `0x8520`

## string_xrefs

- `0x70ea`: `USE_READ_FORM`
- `0x70fa`: `IS_PATHBASEDURLS`

## pseudocode

```c

```

## disassembly

```asm
0x7070  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7075  stloc.0
0x7076  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationId()
0x707b  stloc.1
0x707c  ldarg.0
0x707d  ldstr    aWebResourceOrg// "WEB_RESOURCE_ORG_VERSION_NUMBER"
0x7082  ldloc.1
0x7083  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7088  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x708d  brtrue.s loc_709D
0x708f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceTimestampCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceTimestampCache::Instance()
0x7094  ldloc.1
0x7095  ldloc.0
0x7096  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, string>::LookupEntry(void, var<u1>)
0x709b  br.s     loc_70A2
0x709d  ldstr    asc_3280A// ""
0x70a2  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x70a7  ldstr    aDebugonscripte// "DebugOnScriptError"
0x70ac  ldc.i4.0
0x70ad  box      [mscorlib]System.Int32
0x70b2  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x70b7  unbox.any [mscorlib]System.Int32
0x70bc  ldc.i4.0
0x70bd  cgt
0x70bf  stloc.2
0x70c0  ldarg.0
0x70c1  ldstr    aDebugonscripte_0// "_DebugOnScriptError"
0x70c6  ldloc.2
0x70c7  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x70cc  ldarg.0
0x70cd  ldstr    aOrgUniqueName// "ORG_UNIQUE_NAME"
0x70d2  ldloc.0
0x70d3  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x70d8  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x70dd  ldarg.0
0x70de  ldstr    aOrgId// "ORG_ID"
0x70e3  ldloc.1
0x70e4  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, valuetype [mscorlib]System.Guid varValue)
0x70e9  ldarg.0
0x70ea  ldstr    aUseReadForm// "USE_READ_FORM"
0x70ef  call     bool Microsoft.Crm.Controls.Header::get_UseReadForm()
0x70f4  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x70f9  ldarg.0
0x70fa  ldstr    aIsPathbasedurl// "IS_PATHBASEDURLS"
0x70ff  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsPathBasedURLsEnabled()
0x7104  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x7109  ldarg.0
0x710a  ldstr    aUserHelpLcid// "USER_HELP_LCID"
0x710f  call     int32 Microsoft.Crm.Controls.Header::get_HelpLanguageId()
0x7114  conv.i8
0x7115  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, int64 varValue)
0x711a  ldarg.0
0x711b  ldstr    aUserLanguageCo// "USER_LANGUAGE_CODE"
0x7120  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x7125  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x712a  conv.i8
0x712b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, int64 varValue)
0x7130  ldarg.0
0x7131  ldstr    aIsOutlookClien// "IS_OUTLOOK_CLIENT"
0x7136  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x713b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x7140  ldarg.0
0x7141  ldstr    aIsUeipEnabled// "IS_UEIP_ENABLED"
0x7146  ldarg.0
0x7147  call     instance bool Microsoft.Crm.Controls.Header::IsClientUserExperienceImprovementProgramEnabledForOrg()
0x714c  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x7151  ldarg.0
0x7152  ldstr    aIsOnline// "IS_ONLINE"
0x7157  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x715c  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x7161  ldarg.0
0x7162  ldstr    aIsSandboxOrg// "IS_SANDBOX_ORG"
0x7167  ldloc.1
0x7168  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSandboxOrganization(valuetype [mscorlib]System.Guid)
0x716d  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x7172  ldarg.0
0x7173  ldstr    aIsSupportOrg// "IS_SUPPORT_ORG"
0x7178  ldloc.1
0x7179  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSupportOrganization(valuetype [mscorlib]System.Guid)
0x717e  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x7183  ldarg.0
0x7184  ldstr    aIsPreviewOrg// "IS_PREVIEW_ORG"
0x7189  ldloc.1
0x718a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsPreviewOrganization(valuetype [mscorlib]System.Guid)
0x718f  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x7194  ldarg.0
0x7195  ldstr    aIsPreserveIfra// "IS_PRESERVE_IFRAME"
0x719a  ldloc.0
0x719b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsPreserveIFrameFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x71a0  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x71a5  ldarg.0
0x71a6  ldstr    aIsEmailConvers// "IS_EMAIL_CONVERSATION_FCB"
0x71ab  ldloc.0
0x71ac  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsEmailConversationViewFCB(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x71b1  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x71b6  ldarg.0
0x71b7  ldstr    aIsActivitySort// "IS_ACTIVITY_SORTING"
0x71bc  ldloc.0
0x71bd  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsActivityWallSortingFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x71c2  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x71c7  ldarg.0
0x71c8  ldstr    aIsGridWithImag// "IS_GRID_WITH_IMAGE"
0x71cd  ldloc.0
0x71ce  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsGridWithImageRenderingFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x71d3  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x71d8  ldarg.0
0x71d9  ldstr    aIsAutoCapture// "IS_AUTO_CAPTURE"
0x71de  ldloc.0
0x71df  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsAutoDataCaptureFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x71e4  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x71e9  ldarg.0
0x71ea  ldstr    aIsTextWrapEnab// "IS_TEXT_WRAP_ENABLED"
0x71ef  ldloc.1
0x71f0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsTextWrapEnabledForOrganization(valuetype [mscorlib]System.Guid)
0x71f5  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x71fa  ldarg.0
0x71fb  ldstr    aIsWebclientVis// "IS_WEBCLIENT_VISUAL_REFRESH_ENABLED"
0x7200  ldloc.0
0x7201  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7206  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x720b  ldarg.0
0x720c  ldstr    aIsGreyShadeOnr// "IS_GREY_SHADE_ONRESIZE_ENABLED"
0x7211  ldc.i4.1
0x7212  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x7217  ldarg.0
0x7218  ldstr    aIsRecentlyView// "IS_RECENTLY_VIEW_ENABLED"
0x721d  ldloc.0
0x721e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsEnableRecentlyViewedFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7223  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x7228  ldarg.0
0x7229  call     instance bool Microsoft.Crm.Controls.Header::get_IsLayoutPage()
0x722e  brtrue.s loc_7240
0x7230  ldarg.0
0x7231  ldstr    aReqId// "REQ_ID"
0x7236  call     string [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentRequestId()
0x723b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x7240  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x7245  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x724a  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x724f  brtrue.s loc_7258
0x7251  ldstr    aLtr_0// "LTR"
0x7256  br.s     loc_725D
0x7258  ldstr    aRtl_0// "RTL"
0x725d  stloc.3
0x725e  ldarg.0
0x725f  ldstr    aLocidUiDir// "LOCID_UI_DIR"
0x7264  ldloc.3
0x7265  ldc.i4.0
0x7266  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x726b  ldarg.0
0x726c  ldstr    aVersionStamp// "VERSION_STAMP"
0x7271  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_StaticFileVersionStamp()
0x7276  conv.i8
0x7277  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, int64 varValue)
0x727c  ldarg.0
0x727d  ldstr    aIscarinafeatur// "IsCarinaFeatureAvailable"
0x7282  ldloc.0
0x7283  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsKnowledgebaseFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7288  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x728d  ldarg.0
0x728e  ldstr    aIsparatureatri// "IsParatureAtriaDependenciesAvailable"
0x7293  ldloc.0
0x7294  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsParatureAtriaDependenciesAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7299  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x729e  ldarg.0
0x729f  ldstr    aIscorsenabledf// "IsCorsEnabledForKmControl"
0x72a4  ldstr    aEnablecorsfork// "EnableCorsForKmControl"
0x72a9  ldc.i4.0
0x72aa  box      [mscorlib]System.Int32
0x72af  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x72b4  unbox.any [mscorlib]System.Int32
0x72b9  conv.i8
0x72ba  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, int64 varValue)
0x72bf  ldarg.0
0x72c0  ldstr    aIsvAdditionalA// "ISV_ADDITIONAL_AUTH"
0x72c5  ldarg.0
0x72c6  call     instance string Microsoft.Crm.Controls.Header::BuildExternalAuthParameters()
0x72cb  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x72d0  ldarg.0
0x72d1  ldstr    aIscurrentkmpar// "IsCurrentKMParature"
0x72d6  ldloc.0
0x72d7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsCurrentKMParature(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x72dc  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x72e1  ldarg.0
0x72e2  ldstr    aIsparatureknow// "IsParatureKnowledgebaseVisable"
0x72e7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsParatureKnowledgebaseVisable()
0x72ec  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x72f1  ldloc.0
0x72f2  call     int32[] [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetCustomETCList(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x72f7  stloc.s  4
0x72f9  ldloc.s  4
0x72fb  brfalse.s loc_7323
0x72fd  ldloc.s  4
0x72ff  ldlen
0x7300  brfalse.s loc_7323
0x7302  ldarg.0
0x7303  ldstr    aCustomEtcList// "CUSTOM_ETC_LIST"
0x7308  ldstr    a0_0// "[{0}]"
0x730d  ldstr    asc_2B428// ","
0x7312  ldloc.s  4
0x7314  call     T0x2B000010
0x7319  call     string [mscorlib]System.String::Format(string, object)
0x731e  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x7323  ldloc.0
0x7324  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWidgetManagerFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7329  brfalse.s loc_734F
0x732b  ldarg.0
0x732c  ldstr    aCollapsedwidth// "CollapsedWidth"
0x7331  ldarg.0
0x7332  ldc.i4.0
0x7333  call     instance string Microsoft.Crm.Controls.Header::GetWidgetWidth(int32 state)
0x7338  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x733d  ldarg.0
0x733e  ldstr    aExpandedwidth// "ExpandedWidth"
0x7343  ldarg.0
0x7344  ldc.i4.1
0x7345  call     instance string Microsoft.Crm.Controls.Header::GetWidgetWidth(int32 state)
0x734a  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x734f  ldloc.0
0x7350  brfalse  loc_75CB
0x7355  ldloc.0
0x7356  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_IsUserAuthenticated()
0x735b  brfalse  loc_75CB
0x7360  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x7365  ldloc.0
0x7366  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x736b  ldloc.0
0x736c  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x7371  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x7376  stloc.s  5
0x7378  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x737d  ldc.i4.0
0x737e  ldloc.0
0x737f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x7384  ldloc.s  5
0x7386  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, bool> [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::GetAllFeatureStatus(valuetype [Microsoft.Crm.Core]Microsoft.Crm.FeatureLocation, valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x738b  stloc.s  6
0x738d  ldloc.s  6
0x738f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x7394  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x7399  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MocaOffline()
0x739e  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x73a3  ldloc.0
0x73a4  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsMocaOfflineFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x73a9  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0x73ae  ldloc.s  6
0x73b0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x73b5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x73ba  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_WebresourceLocalizationAndDependency()
0x73bf  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x73c4  ldloc.0
0x73c5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebresourceLocalizationAndDependencyFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x73ca  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0x73cf  ldloc.s  6
0x73d1  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x73d6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x73db  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_WebClientVisualRefresh()
0x73e0  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x73e5  ldloc.0
0x73e6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x73eb  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0x73f0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x73f5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x73fa  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_BackStackForTurboForm()
0x73ff  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7404  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7409  stloc.s  7
0x740b  ldloc.s  6
0x740d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x7412  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x7417  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_BackStackForTurboForm()
0x741c  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x7421  ldloc.s  7
0x7423  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0x7428  ldloc.s  6
0x742a  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x742f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x7434  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ServiceCaseTopicAnalysis()
0x7439  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x743e  ldloca.s 8
0x7440  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, bool>::TryGetValue(var<u1>, !!T0)
0x7445  brfalse.s loc_746F
0x7447  ldloc.s  6
0x7449  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x744e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x7453  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ServiceCaseTopicAnalysis()
0x7458  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x745d  ldloc.s  8
0x745f  brfalse.s loc_7469
0x7461  ldloc.0
0x7462  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsTextAnalyticsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7467  br.s     loc_746A
0x7469  ldc.i4.0
0x746a  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, bool>::set_Item(var<u1>, !!T0)
0x746f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x7474  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x7479  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EmailEngagement()
0x747e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7483  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7488  stloc.s  9
  ... truncated ...
```
