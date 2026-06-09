# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddGlobalVariables

- ea: `0x1a050`
- end: `0x1a418`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddGlobalVariables`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1a700`

## callees

- `0x19f10`
- `0x19f20`
- `0x19f40`
- `0x19fc0`
- `0x1a050`
- `0x1a420`
- `0x1a550`
- `0x1a5b0`

## string_xrefs

- `0x1a0f3`: `CRM2007_WEBSERVICE_NS`
- `0x1a0f8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1a109`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x1a16f`: `CONFIGURABLE_THEME_URL`
- `0x1a1df`: `common.scripts.global.js.NotRecognizedObjectType`
- `0x1a23e`: `common.scripts.global.js.NotRecognizedObjectType`
- `0x1a223`: `IS_PATHBASEDURLS`
- `0x1a39d`: `ORG_SKYPE_PROTOCOL`

## pseudocode

```c

```

## disassembly

```asm
0x1a050  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a055  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::GetSettings(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a05a  stloc.0
0x1a05b  ldarg.0
0x1a05c  ldarg.1
0x1a05d  ldstr    aUserGuid// "USER_GUID"
0x1a062  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x1a067  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x1a06c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x1a071  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a076  ldarg.0
0x1a077  ldarg.1
0x1a078  ldstr    aUserName// "USER_NAME"
0x1a07d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x1a082  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0x1a087  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a08c  ldarg.0
0x1a08d  ldarg.1
0x1a08e  ldstr    aOrgLanguageCod// "ORG_LANGUAGE_CODE"
0x1a093  ldloc.0
0x1a094  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x1a099  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, int32 varValue)
0x1a09e  ldarg.0
0x1a09f  ldarg.1
0x1a0a0  ldstr    aOrgUniqueName// "ORG_UNIQUE_NAME"
0x1a0a5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a0aa  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a0af  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a0b4  ldarg.0
0x1a0b5  ldarg.1
0x1a0b6  ldstr    aServerUrl// "SERVER_URL"
0x1a0bb  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetWebServer()
0x1a0c0  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a0c5  ldarg.0
0x1a0c6  ldarg.1
0x1a0c7  ldstr    aUserLanguageCo// "USER_LANGUAGE_CODE"
0x1a0cc  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1a0d1  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1a0d6  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, int32 varValue)
0x1a0db  ldarg.0
0x1a0dc  ldarg.1
0x1a0dd  ldstr    aUserRoles// "USER_ROLES"
0x1a0e2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x1a0e7  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_Roles()
0x1a0ec  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVarArray(class [mscorlib]System.Text.StringBuilder builder, string varId, class [mscorlib]System.Collections.IEnumerable arrayItems)
0x1a0f1  ldarg.0
0x1a0f2  ldarg.1
0x1a0f3  ldstr    aCrm2007Webserv// "CRM2007_WEBSERVICE_NS"
0x1a0f8  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1a0fd  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a102  ldarg.0
0x1a103  ldarg.1
0x1a104  ldstr    aCrm2007Coretyp// "CRM2007_CORETYPES_NS"
0x1a109  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x1a10e  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a113  ldarg.0
0x1a114  ldarg.1
0x1a115  ldstr    aAuthentication// "AUTHENTICATION_TYPE"
0x1a11a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a11f  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_AuthenticationType()
0x1a124  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, int32 varValue)
0x1a129  ldarg.0
0x1a12a  ldarg.1
0x1a12b  ldstr    aCurrentThemeTy// "CURRENT_THEME_TYPE"
0x1a130  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x1a135  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_CurrentThemeType()
0x1a13a  stloc.3
0x1a13b  ldloca.s 3
0x1a13d  constrained. [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Themes.ThemeType
0x1a143  callvirt instance string [mscorlib]System.Object::ToString()
0x1a148  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a14d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1a152  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1a157  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_Theme()
0x1a15c  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0x1a161  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a166  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a16b  brfalse.s loc_1A17E
0x1a16d  ldarg.0
0x1a16e  ldarg.1
0x1a16f  ldstr    aConfigurableTh// "CONFIGURABLE_THEME_URL"
0x1a174  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetConfigurableThemeStyleSheetUrl()
0x1a179  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a17e  ldarg.0
0x1a17f  ldarg.1
0x1a180  ldstr    aCurrentWebThem// "CURRENT_WEB_THEME"
0x1a185  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetWebTheme()
0x1a18a  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a18f  ldarg.0
0x1a190  ldarg.1
0x1a191  ldstr    aIsOutlookClien// "IS_OUTLOOK_CLIENT"
0x1a196  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x1a19b  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a1a0  ldarg.0
0x1a1a1  ldarg.1
0x1a1a2  ldstr    aIsOutlookLapto// "IS_OUTLOOK_LAPTOP_CLIENT"
0x1a1a7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookFatClient()
0x1a1ac  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a1b1  ldarg.0
0x1a1b2  ldarg.1
0x1a1b3  ldstr    aIsOutlook14Cli// "IS_OUTLOOK_14_CLIENT"
0x1a1b8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlook14Client()
0x1a1bd  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a1c2  ldarg.0
0x1a1c3  ldarg.1
0x1a1c4  ldstr    aIsOnline// "IS_ONLINE"
0x1a1c9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x1a1ce  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a1d3  ldarg.0
0x1a1d4  ldarg.1
0x1a1d5  ldstr    aLocidUnrecogni// "LOCID_UNRECOGNIZE_DOTC"
0x1a1da  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1a1df  ldstr    aCommonScriptsG// "common.scripts.global.js.NotRecognizedO"...
0x1a1e4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1a1e9  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a1ee  ldarg.0
0x1a1ef  ldarg.1
0x1a1f0  ldstr    aEditPreload// "EDIT_PRELOAD"
0x1a1f5  call     bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.BasicHeader::get_PreloadEdit()
0x1a1fa  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a1ff  ldarg.0
0x1a200  ldarg.1
0x1a201  ldstr    aWebServerHost// "WEB_SERVER_HOST"
0x1a206  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetWebServerHostName()
0x1a20b  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a210  ldarg.0
0x1a211  ldarg.1
0x1a212  ldstr    aWebServerPort// "WEB_SERVER_PORT"
0x1a217  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetWebServerPort()
0x1a21c  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, int32 varValue)
0x1a221  ldarg.0
0x1a222  ldarg.1
0x1a223  ldstr    aIsPathbasedurl// "IS_PATHBASEDURLS"
0x1a228  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsPathBasedURLsEnabled()
0x1a22d  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a232  ldarg.0
0x1a233  ldarg.1
0x1a234  ldstr    aLocidUnrecogni// "LOCID_UNRECOGNIZE_DOTC"
0x1a239  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1a23e  ldstr    aCommonScriptsG// "common.scripts.global.js.NotRecognizedO"...
0x1a243  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1a248  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a24d  ldarg.0
0x1a24e  ldarg.1
0x1a24f  ldstr    aEditPreload// "EDIT_PRELOAD"
0x1a254  call     bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.BasicHeader::get_PreloadEdit()
0x1a259  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a25e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationId()
0x1a263  stloc.1
0x1a264  ldarg.0
0x1a265  ldarg.1
0x1a266  ldstr    aWebResourceOrg// "WEB_RESOURCE_ORG_VERSION_NUMBER"
0x1a26b  ldloc.1
0x1a26c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a271  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a276  brtrue.s loc_1A28A
0x1a278  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceTimestampCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WebResourceTimestampCache::Instance()
0x1a27d  ldloc.1
0x1a27e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a283  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, string>::LookupEntry(void, var<u1>)
0x1a288  br.s     loc_1A28F
0x1a28a  ldstr    asc_1F1DE// ""
0x1a28f  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a294  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0x1a299  stloc.s  4
0x1a29b  ldloca.s 4
0x1a29d  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x1a2a2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1a2a7  stloc.s  4
0x1a2a9  ldloca.s 4
0x1a2ab  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x1a2b0  sub
0x1a2b1  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int64)
0x1a2b6  stloc.s  5
0x1a2b8  ldloca.s 5
0x1a2ba  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x1a2bf  stloc.2
0x1a2c0  ldarg.0
0x1a2c1  ldarg.1
0x1a2c2  ldstr    aApplicationFul// "APPLICATION_FULL_VERSION"
0x1a2c7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x1a2cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_FullVersion()
0x1a2d1  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a2d6  ldarg.0
0x1a2d7  ldarg.1
0x1a2d8  ldstr    aIsLive// "IS_LIVE"
0x1a2dd  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsLive()
0x1a2e2  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a2e7  ldarg.0
0x1a2e8  ldarg.1
0x1a2e9  ldstr    aBisosdporg// "_bIsOsdpOrg"
0x1a2ee  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOsdpOrganization()
0x1a2f3  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a2f8  ldarg.0
0x1a2f9  ldarg.1
0x1a2fa  ldstr    aUserTimezoneOf// "USER_TIMEZONE_OFFSET"
0x1a2ff  ldloca.s 2
0x1a301  call     instance string [mscorlib]System.Double::ToString()
0x1a306  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a30b  ldarg.0
0x1a30c  ldarg.1
0x1a30d  ldstr    aUserIsGuidedHe// "USER_IS_GUIDED_HELP_ENABLED"
0x1a312  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x1a317  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsGuidedHelpEnabled()
0x1a31c  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a321  ldarg.0
0x1a322  ldarg.1
0x1a323  ldstr    aUserDefaultCou// "USER_DEFAULT_COUNTRY_CODE"
0x1a328  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x1a32d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_DefaultCountryCodeValue()
0x1a332  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a337  ldarg.0
0x1a338  ldarg.1
0x1a339  ldstr    aLocidUiDir// "LOCID_UI_DIR"
0x1a33e  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1a343  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x1a348  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x1a34d  brtrue.s loc_1A356
0x1a34f  ldstr    aLtr// "LTR"
0x1a354  br.s     loc_1A35B
0x1a356  ldstr    aRtl// "RTL"
0x1a35b  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a360  ldarg.0
0x1a361  ldarg.1
0x1a362  ldstr    aUserTransactio// "USER_TRANSACTION_CURRENCY_ID"
0x1a367  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x1a36c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TransactionCurrencyId()
0x1a371  stloc.s  6
0x1a373  ldloca.s 6
0x1a375  constrained. [mscorlib]System.Guid
0x1a37b  callvirt instance string [mscorlib]System.Object::ToString()
0x1a380  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a385  ldarg.0
0x1a386  ldarg.1
0x1a387  ldstr    aAutoSaveEnable// "AUTO_SAVE_ENABLED"
0x1a38c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x1a391  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsAutoSaveEnabled()
0x1a396  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a39b  ldarg.0
0x1a39c  ldarg.1
0x1a39d  ldstr    aOrgSkypeProtoc// "ORG_SKYPE_PROTOCOL"
0x1a3a2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x1a3a7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_UseSkypeProtocol()
0x1a3ac  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a3b1  ldarg.0
0x1a3b2  ldarg.1
0x1a3b3  ldstr    aOrgDefaultCoun// "ORG_DEFAULT_COUNTRY_CODE"
0x1a3b8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x1a3bd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_DefaultCountryCodeValue()
0x1a3c2  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a3c7  ldarg.0
0x1a3c8  ldarg.1
0x1a3c9  ldstr    aOrgAttributes// "ORG_ATTRIBUTES"
0x1a3ce  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x1a3d3  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAllAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings)
0x1a3d8  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a3dd  ldarg.0
0x1a3de  ldarg.1
0x1a3df  ldstr    aOrgBaseCurrenc// "ORG_BASE_CURRENCY_ID"
0x1a3e4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x1a3e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_BaseCurrencyId()
0x1a3ee  stloc.s  6
0x1a3f0  ldloca.s 6
0x1a3f2  constrained. [mscorlib]System.Guid
0x1a3f8  callvirt instance string [mscorlib]System.Object::ToString()
0x1a3fd  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a402  ldarg.0
0x1a403  ldarg.1
0x1a404  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddAppModuleGlobalVariables(class [mscorlib]System.Text.StringBuilder scriptBuilder)
0x1a409  ldarg.0
0x1a40a  ldarg.1
0x1a40b  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddYammerGlobalVariables(class [mscorlib]System.Text.StringBuilder scriptBuilder)
0x1a410  ldarg.0
0x1a411  ldarg.1
0x1a412  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddActionHubGlobalVariable(class [mscorlib]System.Text.StringBuilder scriptBuilder)
0x1a417  ret
```
