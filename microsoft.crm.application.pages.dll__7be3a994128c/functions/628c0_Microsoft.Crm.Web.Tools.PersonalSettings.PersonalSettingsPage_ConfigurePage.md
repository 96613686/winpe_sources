# Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::ConfigurePage

- ea: `0x628c0`
- end: `0x62fc0`
- name: `Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::ConfigurePage`
- size: `1792`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x628c0`
- `0x62fe0`
- `0x63100`
- `0x63700`
- `0x644d0`
- `0x64f30`
- `0x65290`
- `0x652b0`
- `0x652d0`
- `0x65310`

## string_xrefs

- `0x62cb6`: `/Tools/PersonalSettings/cmds/cmd_update.aspx`
- `0x62cdb`: `/Tools/PersonalSettings/cmds/cmd_update.aspx`
- `0x629dc`: `incomingemailfilteringmethod`
- `0x62bcf`: `LOCID_USRDESC_SERVICE`
- `0x62ceb`: `/Tools/PersonalSettings/cmds/cmd_updateOutlookSyncFilters.aspx`
- `0x62cfb`: `/Tools/PersonalSettings/cmds/cmd_updatePrimaryClient.aspx`
- `0x62d0b`: `/Tools/PersonalSettings/cmds/cmd_updateUserEntityUISettings.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x628c0  ldarg.0
0x628c1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x628c6  ldarg.0
0x628c7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x628cc  brtrue.s loc_628DD
0x628ce  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x628d3  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ReportingPreference [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_ScriptErrorReportingPreference()
0x628d8  ldc.i4.0
0x628d9  ceq
0x628db  br.s     loc_628DE
0x628dd  ldc.i4.1
0x628de  stfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::showPrivacyTab
0x628e3  ldarg.0
0x628e4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x628e9  ldstr    aStaticToolsPer// "/_static/tools/personalsettings/scripts"...
0x628ee  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x628f3  ldarg.0
0x628f4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x628f9  ldstr    aBnavtoprivacy// "bNavToPrivacy"
0x628fe  ldarg.0
0x628ff  ldfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::showPrivacyTab
0x62904  brfalse.s loc_62920
0x62906  ldarg.0
0x62907  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6290c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x62911  ldstr    aPrivacy// "privacy"
0x62916  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6291b  ldnull
0x6291c  cgt.un
0x6291e  br.s     loc_62921
0x62920  ldc.i4.0
0x62921  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x62926  ldarg.0
0x62927  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6292c  ldstr    aBnavtooc// "bNavToOC"
0x62931  ldarg.0
0x62932  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x62937  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x6293c  ldstr    aOc// "oc"
0x62941  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62946  ldnull
0x62947  cgt.un
0x62949  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x6294e  ldarg.0
0x6294f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62954  ldstr    aLocidCheckCoun// "LOCID_CHECK_COUNTRY_CODE_VALUE"
0x62959  ldarg.0
0x6295a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6295f  ldstr    aDefaultcountry// "DefaultCountryCode_Error"
0x62964  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x62969  ldc.i4.0
0x6296a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6296f  ldarg.0
0x62970  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62975  ldstr    aLocidHomePageS// "LOCID_HOME_PAGE_SUB_AREA_DEFAULT"
0x6297a  ldarg.0
0x6297b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x62980  ldstr    aWebToolsPerson_0// "Web.Tools.personalsettings.dialogs.pers"...
0x62985  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6298a  ldc.i4.0
0x6298b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62990  ldarg.0
0x62991  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x62996  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.ElasticSearchIndexUtility::IsElasticSearchEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6299b  stfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::IsExternalSearchEnabled
0x629a0  ldarg.0
0x629a1  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.SearchUtility::GetSearchInfo()
0x629a6  brtrue.s loc_629AB
0x629a8  ldc.i4.0
0x629a9  br.s     loc_629B5
0x629ab  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.SearchUtility::GetSearchInfo()
0x629b0  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations::get_IsEnabled()
0x629b5  stfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::IsCustomSearchEnabled
0x629ba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x629bf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x629c4  ldstr    aUsersettings// "usersettings"
0x629c9  ldc.i4.1
0x629ca  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x629cf  stloc.0
0x629d0  ldarg.0
0x629d1  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::selectIncomingEmailFilteringMethod
0x629d6  ldloc.0
0x629d7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x629dc  ldstr    aIncomingemailf// "incomingemailfilteringmethod"
0x629e1  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x629e6  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x629eb  ldarg.0
0x629ec  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::selectIncomingEmailFilteringMethod
0x629f1  ldarg.0
0x629f2  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x629f7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IncomingEmailFilteringMethod()
0x629fc  box      [mscorlib]System.Int32
0x62a01  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x62a06  ldarg.0
0x62a07  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::searchExperienceValue
0x62a0c  ldloc.0
0x62a0d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x62a12  ldstr    aDefaultsearche// "defaultsearchexperience"
0x62a17  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x62a1c  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x62a21  ldarg.0
0x62a22  ldfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::IsExternalSearchEnabled
0x62a27  brtrue.s loc_62A4E
0x62a29  ldarg.0
0x62a2a  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::searchExperienceValue
0x62a2f  ldc.i4.0
0x62a30  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::RemoveItemByValue(int32)
0x62a35  ldarg.0
0x62a36  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x62a3b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_DefaultSearchExperience()
0x62a40  brtrue.s loc_62A4E
0x62a42  ldarg.0
0x62a43  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x62a48  ldc.i4.1
0x62a49  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::set_DefaultSearchExperience(int32)
0x62a4e  ldarg.0
0x62a4f  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::searchExperienceValue
0x62a54  ldc.i4.3
0x62a55  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::RemoveItemByValue(int32)
0x62a5a  ldarg.0
0x62a5b  ldfld    bool Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::IsCustomSearchEnabled
0x62a60  brtrue.s loc_62A7E
0x62a62  ldarg.0
0x62a63  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x62a68  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_DefaultSearchExperience()
0x62a6d  ldc.i4.3
0x62a6e  bne.un.s loc_62A94
0x62a70  ldarg.0
0x62a71  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x62a76  ldc.i4.1
0x62a77  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::set_DefaultSearchExperience(int32)
0x62a7c  br.s     loc_62A94
0x62a7e  ldarg.0
0x62a7f  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::searchExperienceValue
0x62a84  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.SearchUtility::GetSearchInfo()
0x62a89  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.GlobalSearchConfigurations::get_SearchProviderName()
0x62a8e  ldc.i4.3
0x62a8f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::AddItem(string, int32)
0x62a94  ldarg.0
0x62a95  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::searchExperienceValue
0x62a9a  ldarg.0
0x62a9b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x62aa0  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_DefaultSearchExperience()
0x62aa5  box      [mscorlib]System.Int32
0x62aaa  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x62aaf  ldarg.0
0x62ab0  call     instance void Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::ConfigureRegionalOptions()
0x62ab5  ldarg.0
0x62ab6  call     instance void Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::ConfigureAutoDataCaptureFeature()
0x62abb  ldarg.0
0x62abc  ldfld    class Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::ckEnableHighContrastImages
0x62ac1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x62ac6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0x62acb  ldc.i4.0
0x62acc  ceq
0x62ace  callvirt instance void Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector::set_Checked(bool value)
0x62ad3  ldarg.0
0x62ad4  ldfld    class Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::ckEnableResourceBookingSync
0x62ad9  ldarg.0
0x62ada  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x62adf  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsResourceBookingExchangeSyncEnabled()
0x62ae4  callvirt instance void Microsoft.Crm.Web.Tools.PersonalSettings.CheckBoxSettingSelector::set_Checked(bool value)
0x62ae9  ldarg.0
0x62aea  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Hidden Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::privacyOption
0x62aef  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x62af4  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ReportingPreference [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_ScriptErrorReportingPreference()
0x62af9  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ReportingPreference
0x62afe  ldstr    aD// "D"
0x62b03  call     instance string [mscorlib]System.Enum::ToString(string)
0x62b08  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Hidden::set_Text(string)
0x62b0d  ldarg.0
0x62b0e  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::transCurId
0x62b13  ldc.i4.1
0x62b14  newarr   [mscorlib]System.Int32
0x62b19  dup
0x62b1a  ldc.i4.0
0x62b1b  ldc.i4   0x2391
0x62b20  stelem.i4
0x62b21  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x62b26  ldarg.0
0x62b27  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x62b2c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsDefaultCurrencyForUserNull()
0x62b31  brtrue.s loc_62B6D
0x62b33  ldarg.0
0x62b34  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Web.Tools.PersonalSettings.PersonalSettingsPage::transCurId
0x62b39  ldarg.0
0x62b3a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x62b3f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TransactionCurrencyId()
0x62b44  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x62b49  ldc.i4   0x2391
0x62b4e  ldarg.0
0x62b4f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x62b54  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TransactionCurrencyId()
0x62b59  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x62b5e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetCurrencyName(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x62b63  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor(string, int32, string)
0x62b68  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x62b6d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x62b72  brtrue   loc_62CC5
0x62b77  ldarg.0
0x62b78  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62b7d  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x62b82  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62b87  ldarg.0
0x62b88  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62b8d  ldstr    aLocidUsrdescSa// "LOCID_USRDESC_SALES"
0x62b92  ldarg.0
0x62b93  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x62b98  ldstr    aWebToolsPerson_1// "Web.Tools.personalsettings.dialogs.pers"...
0x62b9d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x62ba2  ldc.i4.0
0x62ba3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62ba8  ldarg.0
0x62ba9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62bae  ldstr    aLocidUsrdescMa// "LOCID_USRDESC_MARKETING"
0x62bb3  ldarg.0
0x62bb4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x62bb9  ldstr    aWorkplaceStyle// "Workplace_Style_Marketing_User_Descript"...
0x62bbe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x62bc3  ldc.i4.0
0x62bc4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62bc9  ldarg.0
0x62bca  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62bcf  ldstr    aLocidUsrdescSe// "LOCID_USRDESC_SERVICE"
0x62bd4  ldarg.0
0x62bd5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x62bda  ldstr    aWebToolsPerson_2// "Web.Tools.personalsettings.dialogs.pers"...
0x62bdf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x62be4  ldc.i4.0
0x62be5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62bea  ldarg.0
0x62beb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62bf0  ldstr    aLocidItemsEmai// "LOCID_ITEMS_EMAIL"
0x62bf5  ldarg.0
0x62bf6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x62bfb  ldstr    aWebToolsPerson_3// "Web.Tools.personalsettings.dialogs.pers"...
0x62c00  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x62c05  ldc.i4.0
0x62c06  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62c0b  ldarg.0
0x62c0c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62c11  ldstr    aLocidItemsDraf// "LOCID_ITEMS_DRAFTEMAIL"
0x62c16  ldarg.0
0x62c17  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x62c1c  ldstr    aWebToolsPerson_4// "Web.Tools.personalsettings.dialogs.pers"...
0x62c21  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x62c26  ldc.i4.0
0x62c27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62c2c  ldarg.0
0x62c2d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62c32  ldstr    aLocidItemsAssi// "LOCID_ITEMS_ASSIGNED"
0x62c37  ldarg.0
0x62c38  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x62c3d  ldstr    aWebToolsPerson_5// "Web.Tools.personalsettings.dialogs.pers"...
0x62c42  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x62c47  ldc.i4.0
0x62c48  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62c4d  ldarg.0
0x62c4e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62c53  ldstr    aLocidItemsInpr// "LOCID_ITEMS_INPROGRESS"
0x62c58  ldarg.0
0x62c59  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x62c5e  ldstr    aWebToolsPerson_6// "Web.Tools.personalsettings.dialogs.pers"...
0x62c63  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x62c68  ldc.i4.0
0x62c69  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62c6e  ldarg.0
0x62c6f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62c74  ldstr    aLocidItemsPass// "LOCID_ITEMS_PASSWORD_MISMATCH"
0x62c79  ldarg.0
0x62c7a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x62c7f  ldstr    aWebToolsPerson_7// "Web.Tools.personalsettings.dialogs.pers"...
0x62c84  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x62c89  ldc.i4.0
0x62c8a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62c8f  ldarg.0
0x62c90  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62c95  ldstr    aLocidMsgEmptyC// "LOCID_MSG_EMPTY_CREDENTIALS"
0x62c9a  ldarg.0
0x62c9b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x62ca0  ldstr    aWebToolsPerson_8// "Web.Tools.personalsettings.dialogs.pers"...
0x62ca5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x62caa  ldc.i4.0
0x62cab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x62cb0  ldarg.0
0x62cb1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62cb6  ldstr    aToolsPersonals// "/Tools/PersonalSettings/cmds/cmd_update"...
0x62cbb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x62cc0  br       loc_62EFE
0x62cc5  ldarg.0
0x62cc6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62ccb  ldstr    aStaticControls_24// "/_static/_controls/multiselect/multisel"...
0x62cd0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x62cd5  ldarg.0
0x62cd6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62cdb  ldstr    aToolsPersonals// "/Tools/PersonalSettings/cmds/cmd_update"...
0x62ce0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x62ce5  ldarg.0
0x62ce6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62ceb  ldstr    aToolsPersonals_0// "/Tools/PersonalSettings/cmds/cmd_update"...
  ... truncated ...
```
