# Microsoft.Crm.Application.Controls.AppHeader::AddGlobalValues

- ea: `0x869d0`
- end: `0x87248`
- name: `Microsoft.Crm.Application.Controls.AppHeader::AddGlobalValues`
- size: `2168`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x67b0`
- `0x6930`
- `0x869d0`
- `0x87250`
- `0x872a0`
- `0x87390`
- `0x87550`

## string_xrefs

- `0x86a50`: `IS_PATHBASEDURLS`
- `0x86b6a`: `APP_MODULE_WELCOME_ID`
- `0x86b8c`: `APP_MODULE_WELCOME_NAME`
- `0x86dc3`: `MakeSocialPanePhoneCallCompleted`
- `0x86ddb`: `MakeSocialPanePhoneCallCompleted`
- `0x86e8c`: `ORG_SKYPE_PROTOCOL`
- `0x86ed6`: `CRM2007_WEBSERVICE_NS`
- `0x86edb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x86eeb`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x870f7`: `Ribbon.ShortcutKeyJumpToRibbon_AccessKey`
- `0x87112`: `Ribbon.ShortcutKeyJumpToFirstControl_AccessKey`
- `0x87169`: `CRM_ONLINE_LEGAL_LINK`
- `0x87185`: `CRM_ONLINE_PRIVACY_LINK`

## pseudocode

```c

```

## disassembly

```asm
0x869d0  ldarg.0
0x869d1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.BasicHeader::AddGlobalValues()
0x869d6  ldarg.0
0x869d7  ldstr    aLocidUiDir// "LOCID_UI_DIR"
0x869dc  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x869e1  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x869e6  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x869eb  brtrue.s loc_869F4
0x869ed  ldstr    aLtr// "LTR"
0x869f2  br.s     loc_869F9
0x869f4  ldstr    aRtl// "RTL"
0x869f9  ldc.i4.0
0x869fa  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x869ff  ldarg.0
0x86a00  ldstr    aBisosdporg// "_bIsOsdpOrg"
0x86a05  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOsdpOrganization()
0x86a0a  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86a0f  ldarg.0
0x86a10  ldstr    aIsLive// "IS_LIVE"
0x86a15  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsLive()
0x86a1a  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86a1f  ldarg.0
0x86a20  ldstr    aIsOnpremise// "IS_ONPREMISE"
0x86a25  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnPremise()
0x86a2a  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86a2f  ldarg.0
0x86a30  ldstr    aIsSpla// "IS_SPLA"
0x86a35  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSpla()
0x86a3a  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86a3f  ldarg.0
0x86a40  ldstr    aIsClaims// "IS_CLAIMS"
0x86a45  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsClaims()
0x86a4a  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86a4f  ldarg.0
0x86a50  ldstr    aIsPathbasedurl// "IS_PATHBASEDURLS"
0x86a55  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsPathBasedURLsEnabled()
0x86a5a  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86a5f  ldarg.0
0x86a60  ldstr    aOrgUniqueName// "ORG_UNIQUE_NAME"
0x86a65  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86a6a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x86a6f  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86a74  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x86a79  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x86a7e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppModuleForOrganization()
0x86a83  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86a88  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x86a8d  brfalse  loc_86BA2
0x86a92  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86a97  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_CurrentAppId()
0x86a9c  stloc.s  0xB
0x86a9e  ldloc.s  0xB
0x86aa0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x86aa5  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x86aaa  brfalse  loc_86BA2
0x86aaf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86ab4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppDataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x86ab9  ldloc.s  0xB
0x86abb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86ac0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleCache::LookupEntry(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x86ac5  stloc.s  0xC
0x86ac7  ldarg.0
0x86ac8  ldstr    aAppModuleUniqu// "APP_MODULE_UNIQUE_NAME"
0x86acd  ldloc.s  0xC
0x86acf  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_UniqueName()
0x86ad4  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86ad9  ldarg.0
0x86ada  ldstr    aAppModuleAppid// "APP_MODULE_APPID"
0x86adf  ldloc.s  0xC
0x86ae1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x86ae6  stloc.s  0xD
0x86ae8  ldloca.s 0xD
0x86aea  constrained. [mscorlib]System.Guid
0x86af0  callvirt instance string [mscorlib]System.Object::ToString()
0x86af5  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86afa  ldarg.0
0x86afb  ldstr    aAppModuleDispl// "APP_MODULE_DISPLAYNAME"
0x86b00  ldloc.s  0xC
0x86b02  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleName()
0x86b07  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86b0c  ldarg.0
0x86b0d  ldstr    aAppModuleUrl// "APP_MODULE_URL"
0x86b12  ldloc.s  0xC
0x86b14  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_Url()
0x86b19  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86b1e  ldloc.s  0xC
0x86b20  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_WebResourceInfo()
0x86b25  brfalse.s loc_86B60
0x86b27  ldarg.0
0x86b28  ldstr    aAppModuleIconI// "APP_MODULE_ICON_ID"
0x86b2d  ldloc.s  0xC
0x86b2f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_WebResourceInfo()
0x86b34  ldflda   valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo::Id
0x86b39  constrained. [mscorlib]System.Guid
0x86b3f  callvirt instance string [mscorlib]System.Object::ToString()
0x86b44  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86b49  ldarg.0
0x86b4a  ldstr    aAppModuleIconN// "APP_MODULE_ICON_NAME"
0x86b4f  ldloc.s  0xC
0x86b51  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_WebResourceInfo()
0x86b56  ldfld    string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo::Name
0x86b5b  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86b60  ldloc.s  0xC
0x86b62  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_WelcomePageInfo()
0x86b67  brfalse.s loc_86BA2
0x86b69  ldarg.0
0x86b6a  ldstr    aAppModuleWelco// "APP_MODULE_WELCOME_ID"
0x86b6f  ldloc.s  0xC
0x86b71  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_WelcomePageInfo()
0x86b76  ldflda   valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo::Id
0x86b7b  constrained. [mscorlib]System.Guid
0x86b81  callvirt instance string [mscorlib]System.Object::ToString()
0x86b86  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86b8b  ldarg.0
0x86b8c  ldstr    aAppModuleWelco_0// "APP_MODULE_WELCOME_NAME"
0x86b91  ldloc.s  0xC
0x86b93  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AppModuleMetadata::get_WelcomePageInfo()
0x86b98  ldfld    string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.WebResourceInfo::Name
0x86b9d  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86ba2  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationId()
0x86ba7  stloc.0
0x86ba8  ldarg.0
0x86ba9  ldstr    aWebResourceOrg// "WEB_RESOURCE_ORG_VERSION_NUMBER"
0x86bae  ldloc.0
0x86baf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x86bb4  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x86bb9  brtrue.s loc_86BCD
0x86bbb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceTimestampCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceTimestampCache::Instance()
0x86bc0  ldloc.0
0x86bc1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86bc6  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, string>::LookupEntry(void, var<u1>)
0x86bcb  br.s     loc_86BD2
0x86bcd  ldstr    asc_F537C// ""
0x86bd2  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86bd7  ldarg.0
0x86bd8  ldstr    aUsetabletexper// "UseTabletExperience"
0x86bdd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86be2  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x86be7  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86bec  ldarg.0
0x86bed  ldstr    aErrorcodesisva// "_ErrorCodesIsvAborted"
0x86bf2  ldstr    a0x// "0x"
0x86bf7  ldc.i4   0x80040265
0x86bfc  stloc.s  0xE
0x86bfe  ldloca.s 0xE
0x86c00  ldstr    aX// "X"
0x86c05  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x86c0a  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x86c0f  call     string [mscorlib]System.String::Concat(string, string)
0x86c14  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86c19  ldarg.0
0x86c1a  ldstr    aScripterrorrep// "ScriptErrorReportingPreference"
0x86c1f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x86c24  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ReportingPreference [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_ScriptErrorReportingPreference()
0x86c29  brfalse.s loc_86C37
0x86c2b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x86c30  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ReportingPreference [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_ScriptErrorReportingPreference()
0x86c35  br.s     loc_86C41
0x86c37  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x86c3c  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ReportingPreference [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_ScriptErrorReportingPreference()
0x86c41  conv.i8
0x86c42  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x86c47  ldarg.0
0x86c48  ldstr    aLocidScriptErr// "LOCID_SCRIPT_ERROR_STATUS_BAR"
0x86c4d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x86c52  ldstr    aScriptErrorSta// "Script_Error_Status_Bar"
0x86c57  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x86c5c  ldc.i4.0
0x86c5d  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x86c62  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x86c67  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsPresenceEnabled()
0x86c6c  stloc.1
0x86c6d  ldarg.0
0x86c6e  ldstr    aBpresenceenabl// "_bPresenceEnabled"
0x86c73  ldloc.1
0x86c74  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86c79  ldloc.1
0x86c7a  brfalse.s loc_86C82
0x86c7c  ldarg.0
0x86c7d  call     instance void Microsoft.Crm.Application.Controls.AppHeader::LoadPresenceEnable()
0x86c82  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x86c87  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsAutoSaveEnabled()
0x86c8c  stloc.2
0x86c8d  ldarg.0
0x86c8e  ldstr    aAutoSaveEnable// "AUTO_SAVE_ENABLED"
0x86c93  ldloc.2
0x86c94  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86c99  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x86c9e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_EnableMicrosoftFlowIntegration()
0x86ca3  brfalse.s loc_86CAF
0x86ca5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x86caa  ldc.i4.0
0x86cab  ceq
0x86cad  br.s     loc_86CB0
0x86caf  ldc.i4.0
0x86cb0  stloc.3
0x86cb1  ldarg.0
0x86cb2  ldstr    aEnableMicrosof// "ENABLE_MICROSOFT_FLOW_INTEGRATION"
0x86cb7  ldloc.3
0x86cb8  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86cbd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x86cc2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MicrosoftFlowEnvironment()
0x86cc7  stloc.s  4
0x86cc9  ldarg.0
0x86cca  ldstr    aMicrosoftFlowI// "MICROSOFT_FLOW_INTEGRATED_ENVIRONMENT"
0x86ccf  ldloc.s  4
0x86cd1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86cd6  ldloc.3
0x86cd7  brfalse.s loc_86D1A
0x86cd9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86cde  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86ce3  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserCulture()
0x86ce8  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x86ced  callvirt instance string [mscorlib]System.String::ToLower()
0x86cf2  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MicrosoftFlowUtils::CreateMicrosoftFlowRuntimeUrl(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, string)
0x86cf7  stloc.s  0xF
0x86cf9  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIUtility::get_FirstPartyIntegrationSiteUrl()
0x86cfe  stloc.s  0x10
0x86d00  ldarg.0
0x86d01  ldstr    aMicrosoftFlowF// "MICROSOFT_FLOW_FIRSTPARTYINTEGRATION_SI"...
0x86d06  ldloc.s  0xF
0x86d08  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86d0d  ldarg.0
0x86d0e  ldstr    aMicrosoftFlowD// "MICROSOFT_FLOW_DESTINATIONURL"
0x86d13  ldloc.s  0x10
0x86d15  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86d1a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x86d1f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_DisplayNavigationTour()
0x86d24  stloc.s  5
0x86d26  ldarg.0
0x86d27  ldstr    aDisplayNavigat// "DISPLAY_NAVIGATION_TOUR"
0x86d2c  ldloc.s  5
0x86d2e  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86d33  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x86d38  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_UseLegacyFormRendering()
0x86d3d  brtrue.s loc_86D42
0x86d3f  ldc.i4.1
0x86d40  br.s     loc_86D43
0x86d42  ldc.i4.0
0x86d43  stloc.s  6
0x86d45  ldarg.0
0x86d46  ldstr    aDisplayTurboFo// "DISPLAY_TURBO_FORM"
0x86d4b  ldloc.s  6
0x86d4d  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86d52  ldarg.0
0x86d53  ldstr    aMetadataTimest// "METADATA_TIMESTAMP"
0x86d58  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86d5d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x86d62  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0x86d67  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86d6c  ldarg.0
0x86d6d  ldstr    aUserTimestamp// "USER_TIMESTAMP"
0x86d72  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x86d77  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86d7c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x86d81  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86d86  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x86d8b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_Timestamp()
0x86d90  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86d95  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x86d9a  ldstr    aChangedoublequ// "ChangeDoubleQuoteToSingleQuote"
0x86d9f  ldc.i4.0
0x86da0  box      [mscorlib]System.Boolean
0x86da5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x86daa  unbox.any [mscorlib]System.Boolean
0x86daf  stloc.s  7
0x86db1  ldarg.0
0x86db2  ldstr    aChangedoublequ// "ChangeDoubleQuoteToSingleQuote"
0x86db7  ldloc.s  7
0x86db9  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86dbe  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x86dc3  ldstr    aMakesocialpane// "MakeSocialPanePhoneCallCompleted"
0x86dc8  ldc.i4.1
0x86dc9  box      [mscorlib]System.Boolean
0x86dce  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x86dd3  unbox.any [mscorlib]System.Boolean
0x86dd8  stloc.s  8
0x86dda  ldarg.0
0x86ddb  ldstr    aMakesocialpane// "MakeSocialPanePhoneCallCompleted"
0x86de0  ldloc.s  8
0x86de2  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x86de7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86dec  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::GetSettings(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x86df1  stloc.s  9
0x86df3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x86df8  brfalse.s loc_86E0C
0x86dfa  ldarg.0
0x86dfb  ldstr    aOrgAttributes// "ORG_ATTRIBUTES"
0x86e00  ldloc.s  9
0x86e02  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAllAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings)
0x86e07  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x86e0c  ldarg.0
0x86e0d  ldstr    aOrgBaseCurrenc// "ORG_BASE_CURRENCY_ID"
0x86e12  ldloc.s  9
0x86e14  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_BaseCurrencyId()
0x86e19  stloc.s  0xD
0x86e1b  ldloca.s 0xD
0x86e1d  constrained. [mscorlib]System.Guid
0x86e23  callvirt instance string [mscorlib]System.Object::ToString()
0x86e28  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
  ... truncated ...
```
