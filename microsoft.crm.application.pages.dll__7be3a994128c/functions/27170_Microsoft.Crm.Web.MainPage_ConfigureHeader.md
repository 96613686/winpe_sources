# Microsoft.Crm.Web.MainPage::ConfigureHeader

- ea: `0x27170`
- end: `0x2750f`
- name: `Microsoft.Crm.Web.MainPage::ConfigureHeader`
- size: `927`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x8cd0`
- `0x254a0`
- `0x27090`
- `0x270a0`
- `0x27170`
- `0x27510`
- `0x27550`
- `0xcaf40`
- `0xcb3f0`

## string_xrefs

- `0x27311`: `/_static/_common/scripts/Performance.js`
- `0x27298`: `UpdateItemTimeZone`
- `0x272c5`: `/_static/_common/scripts/main.js`
- `0x272e1`: `/_static/_common/scripts/widgetmanager.js`
- `0x272f1`: `/_static/_common/scripts/PostMessageCommunication.js`
- `0x27301`: `/_common/styles/main.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x27170  ldarg.0
0x27171  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::ConfigureHeader()
0x27176  ldarg.0
0x27177  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2717c  ldstr    aInitializeNoti// "Initialize NotificationContext"
0x27181  ldstr    aWindowTopNotif// "window.top.notificationContext='Global'"...
0x27186  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x2718b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27190  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::GetSettings(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27195  stloc.0
0x27196  ldarg.0
0x27197  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2719c  ldstr    aOrgAttributes// "ORG_ATTRIBUTES"
0x271a1  ldloc.0
0x271a2  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAllAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings)
0x271a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x271ac  call     bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::IsProperCDNEnvironment()
0x271b1  brfalse.s loc_271B9
0x271b3  call     class [mscorlib]System.Threading.Tasks.Task [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::CheckCDNForSentinelFileAsync()
0x271b8  pop
0x271b9  ldloc.0
0x271ba  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_AllowUsersSeeAppDownloadMessage()
0x271bf  stloc.2
0x271c0  ldloca.s 2
0x271c2  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x271c7  brfalse  loc_27266
0x271cc  ldloc.0
0x271cd  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_AllowUsersSeeAppDownloadMessage()
0x271d2  stloc.2
0x271d3  ldc.i4.1
0x271d4  stloc.3
0x271d5  ldloca.s 2
0x271d7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x271dc  ldloc.3
0x271dd  beq.s    loc_271E2
0x271df  ldc.i4.0
0x271e0  br.s     loc_271E9
0x271e2  ldloca.s 2
0x271e4  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x271e9  brfalse.s loc_27266
0x271eb  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_UseTabletApp()
0x271f0  ldc.i4.3
0x271f1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x271f6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x271fb  brfalse.s loc_27266
0x271fd  ldarg.0
0x271fe  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x27203  ldstr    aMsapplicationI// "msApplication-ID"
0x27208  ldstr    aApp_0// "App"
0x2720d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header::AddGenericMetaTag(string, string)
0x27212  ldarg.0
0x27213  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x27218  ldstr    aMsapplicationO// "msApplication-OptOut"
0x2721d  ldstr    aSwitch// "switch"
0x27222  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header::AddGenericMetaTag(string, string)
0x27227  ldarg.0
0x27228  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2722d  ldstr    aMsapplicationA// "msApplication-Arguments"
0x27232  ldstr    aSwitchtoapp1// "switchtoapp=1"
0x27237  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header::AddGenericMetaTag(string, string)
0x2723c  ldarg.0
0x2723d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x27242  ldstr    aMsapplicationP// "msApplication-PackageFamilyName"
0x27247  ldstr    aMicrosoftMicro// "Microsoft.MicrosoftDynamicsCRMforWindow"...
0x2724c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header::AddGenericMetaTag(string, string)
0x27251  ldarg.0
0x27252  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x27257  ldstr    aAppleItunesApp// "apple-itunes-app"
0x2725c  ldstr    aAppId678800460// "app-id=678800460"
0x27261  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header::AddGenericMetaTag(string, string)
0x27266  ldarg.0
0x27267  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2726c  ldc.i4.2
0x2726d  newarr   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock
0x27272  dup
0x27273  ldc.i4.0
0x27274  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x27279  dup
0x2727a  ldstr    aMainonload// "MainOnLoad"
0x2727f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string)
0x27284  dup
0x27285  ldstr    aMainaspxpageon// "MainAspxPageOnLoad();"
0x2728a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string)
0x2728f  stelem.ref
0x27290  dup
0x27291  ldc.i4.1
0x27292  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x27297  dup
0x27298  ldstr    aUpdateitemtime// "UpdateItemTimeZone"
0x2729d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string)
0x272a2  dup
0x272a3  ldarg.0
0x272a4  call     instance string Microsoft.Crm.Web.MainPage::GetUpdateItemTimeZoneJsBlock()
0x272a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string)
0x272ae  stelem.ref
0x272af  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ScriptBlock[])
0x272b4  ldarg.0
0x272b5  call     instance class Microsoft.Crm.Common.Web.PreloadingHelper Microsoft.Crm.Web.MainPage::get_LoadingHelper()
0x272ba  callvirt instance void Microsoft.Crm.Common.Web.PreloadingHelper::SetDefaultFormModeForRefreshEntities()
0x272bf  ldarg.0
0x272c0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x272c5  ldstr    aStaticCommonSc_9// "/_static/_common/scripts/main.js"
0x272ca  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x272cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x272d4  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWidgetManagerFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x272d9  brfalse.s loc_272FB
0x272db  ldarg.0
0x272dc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x272e1  ldstr    aStaticCommonSc_10// "/_static/_common/scripts/widgetmanager."...
0x272e6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x272eb  ldarg.0
0x272ec  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x272f1  ldstr    aStaticCommonSc_11// "/_static/_common/scripts/PostMessageCom"...
0x272f6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x272fb  ldarg.0
0x272fc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x27301  ldstr    aCommonStylesMa// "/_common/styles/main.css.aspx"
0x27306  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x2730b  ldarg.0
0x2730c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x27311  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Performance.js"
0x27316  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2731b  ldarg.0
0x2731c  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0x27321  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::RenderYammerGlobalVariables()
0x27326  ldarg.0
0x27327  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0x2732c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::RenderActionHubGlobalVariables()
0x27331  ldarg.0
0x27332  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentEntityMetadata()
0x27337  brfalse  loc_2743B
0x2733c  ldarg.0
0x2733d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentEntityMetadata()
0x27342  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x27347  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2734c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27351  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.RibbonUtility::IsEntityUsingRibbon(string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache)
0x27356  stloc.s  4
0x27358  ldarg.0
0x27359  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0x2735e  ldloc.s  4
0x27360  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::set_SuppressRibbonTabs(bool)
0x27365  ldarg.0
0x27366  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2736b  ldstr    aIsEntityRibbon// "IS_ENTITY_RIBBONIZED"
0x27370  ldloc.s  4
0x27372  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x27377  ldloc.s  4
0x27379  brfalse.s loc_27391
0x2737b  ldarg.0
0x2737c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x27381  ldstr    aPerceivedRibbo// "PERCEIVED_RIBBON_KEY"
0x27386  ldarg.0
0x27387  call     instance string Microsoft.Crm.Web.MainPage::GenerateKeyForPerceivedRibbon()
0x2738c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x27391  ldarg.0
0x27392  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x27397  ldstr    aUsername// "USERNAME"
0x2739c  ldarg.0
0x2739d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x273a2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0x273a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x273ac  ldarg.0
0x273ad  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentEntityMetadata()
0x273b2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x273b7  stloc.s  5
0x273b9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x273be  brfalse.s loc_2743B
0x273c0  ldloc.s  5
0x273c2  ldstr    aAppointment// "appointment"
0x273c7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x273cc  brtrue.s loc_27406
0x273ce  ldloc.s  5
0x273d0  ldstr    aRecurringappoi// "recurringappointmentmaster"
0x273d5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x273da  brtrue.s loc_27406
0x273dc  ldloc.s  5
0x273de  ldstr    aEmail// "email"
0x273e3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x273e8  brtrue.s loc_27406
0x273ea  ldloc.s  5
0x273ec  ldstr    aTask// "task"
0x273f1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x273f6  brtrue.s loc_27406
0x273f8  ldloc.s  5
0x273fa  ldstr    aContact// "contact"
0x273ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x27404  brfalse.s loc_2743B
0x27406  ldarg.0
0x27407  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentEntityMetadata()
0x2740c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x27411  call     class Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderFactory::GetConfigHeader(int32 typeCode)
0x27416  ldarg.0
0x27417  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0x2741c  ldarg.0
0x2741d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentEntityMetadata()
0x27422  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x27427  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2742c  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27431  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x27436  callvirt instance void Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader::ConfigHeader(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager header, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0x2743b  ldarg.0
0x2743c  ldfld    bool Microsoft.Crm.Web.MainPage::_newNavBarModeSet
0x27441  brfalse.s loc_27464
0x27443  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x27448  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x2744d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_GuidedHelp()
0x27452  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27457  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2745c  brfalse.s loc_27464
0x2745e  ldarg.0
0x2745f  call     instance void Microsoft.Crm.Web.MainPage::AddGuidedHelpResources()
0x27464  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x27469  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x2746e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_NPSSurvey()
0x27473  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27478  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2747d  brfalse.s loc_27485
0x2747f  ldarg.0
0x27480  call     instance void Microsoft.Crm.Web.MainPage::AddNPSSurveyResources()
0x27485  ldarg.0
0x27486  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2748b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header::SetHelpUrlVars()
0x27490  ldarg.0
0x27491  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0x27496  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Ribbon.RibbonData [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::get_RibbonDataControl()
0x2749b  ldc.i4.1
0x2749c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Ribbon.RibbonData::set_IsDefaultData(bool)
0x274a1  ldarg.0
0x274a2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x274a7  ldstr    aLoadtracker// "loadTracker"
0x274ac  ldstr    aSysApplication_0// "Sys.Application.add_init(function(){\r"...
0x274b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x274b6  call     valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetEntityMetadata()
0x274bb  stloc.1
0x274bc  ldarg.0
0x274bd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x274c2  ldstr    aEntitySetNames// "ENTITY_SET_NAMES"
0x274c7  ldloca.s 1
0x274c9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x274ce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x274d3  ldarg.0
0x274d4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x274d9  ldstr    aEntityPrimaryK// "ENTITY_PRIMARY_KEYS"
0x274de  ldloca.s 1
0x274e0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x274e5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x274ea  ldarg.0
0x274eb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x274f0  ldstr    aLoginRequestCo// "LOGIN_REQUEST_CORRELATIONID"
0x274f5  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x274fa  stloc.s  6
0x274fc  ldloca.s 6
0x274fe  constrained. [mscorlib]System.Guid
0x27504  callvirt instance string [mscorlib]System.Object::ToString()
0x27509  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x2750e  ret
```
