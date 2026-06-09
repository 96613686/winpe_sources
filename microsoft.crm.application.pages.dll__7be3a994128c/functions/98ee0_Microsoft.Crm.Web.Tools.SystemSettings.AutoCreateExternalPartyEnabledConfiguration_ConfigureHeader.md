# Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::ConfigureHeader

- ea: `0x98ee0`
- end: `0x990ab`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::ConfigureHeader`
- size: `459`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x99550`

## string_xrefs

- `0x98efc`: `/_common/styles/dialogs.css.aspx`
- `0x98fe3`: `Button_Label_Remove`
- `0x98eec`: `/_common/styles/global.css.aspx`
- `0x98f2c`: `/Tools/SystemSettings/Dialogs/ExternalPartyEnabledConfiguration.css.aspx`
- `0x98f3c`: `/_static/tools/systemcustomization/scripts/autocreateexternalpartyenabledconfig.js`
- `0x98ffe`: `External_Applications_Setup_RemoveButtonText`
- `0x9901e`: `External_Applications_Setup_RemoveButtonText`

## pseudocode

```c

```

## disassembly

```asm
0x98ee0  ldarg.0
0x98ee1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0x98ee6  ldarg.0
0x98ee7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98eec  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0x98ef1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x98ef6  ldarg.0
0x98ef7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98efc  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x98f01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x98f06  ldarg.0
0x98f07  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98f0c  ldstr    aControlsNaviga// "/_controls/navigation/map.css.aspx"
0x98f11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x98f16  ldarg.0
0x98f17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98f1c  ldstr    aStaticMobileSt// "/_static/mobile/styles/console/global.c"...
0x98f21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x98f26  ldarg.0
0x98f27  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98f2c  ldstr    aToolsSystemset_5// "/Tools/SystemSettings/Dialogs/ExternalP"...
0x98f31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x98f36  ldarg.0
0x98f37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98f3c  ldstr    aStaticToolsSys_5// "/_static/tools/systemcustomization/scri"...
0x98f41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x98f46  ldarg.0
0x98f47  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::ExternalPartyEnabledEntitiesText
0x98f4c  ldarg.0
0x98f4d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98f52  ldstr    aExternalApplic_0// "External_Applications_Setup_AvailableEn"...
0x98f57  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98f5c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x98f61  ldarg.0
0x98f62  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::SelectedAutoCreateExternalPartyEntitiesText
0x98f67  ldarg.0
0x98f68  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98f6d  ldstr    aExternalApplic_1// "External_Applications_Setup_SelectedEnt"...
0x98f72  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98f77  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x98f7c  ldarg.0
0x98f7d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::AddButton
0x98f82  ldarg.0
0x98f83  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98f88  ldstr    aMenuLabelAdd// "Menu_Label_Add"
0x98f8d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98f92  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x98f97  ldarg.0
0x98f98  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::AddButton
0x98f9d  ldarg.0
0x98f9e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98fa3  ldstr    aExternalApplic_2// "External_Applications_Setup_AddButtonTe"...
0x98fa8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98fad  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x98fb2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x98fb7  ldarg.0
0x98fb8  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::AddButton
0x98fbd  ldarg.0
0x98fbe  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98fc3  ldstr    aExternalApplic_2// "External_Applications_Setup_AddButtonTe"...
0x98fc8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98fcd  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x98fd2  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x98fd7  ldarg.0
0x98fd8  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::RemoveButton
0x98fdd  ldarg.0
0x98fde  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98fe3  ldstr    aButtonLabelRem// "Button_Label_Remove"
0x98fe8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98fed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x98ff2  ldarg.0
0x98ff3  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::RemoveButton
0x98ff8  ldarg.0
0x98ff9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98ffe  ldstr    aExternalApplic_3// "External_Applications_Setup_RemoveButto"...
0x99003  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99008  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x9900d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x99012  ldarg.0
0x99013  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::RemoveButton
0x99018  ldarg.0
0x99019  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9901e  ldstr    aExternalApplic_3// "External_Applications_Setup_RemoveButto"...
0x99023  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99028  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x9902d  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x99032  ldarg.0
0x99033  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x99038  ldstr    aLocidFormsSave// "LOCID_FORMS_SAVE_CONFIRM_TITLE"
0x9903d  ldarg.0
0x9903e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x99043  ldstr    aWebFormsStyles_2// "Web._forms.styles.FORM.crm.htc_Title"
0x99048  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9904d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x99052  ldarg.0
0x99053  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x99058  ldstr    aLocidMustSelec// "LOCID_MUST_SELECT_ENTITY_WARNING"
0x9905d  ldarg.0
0x9905e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x99063  ldstr    aExternalApplic_4// "External_Applications_Setup_MustContain"...
0x99068  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9906d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x99072  ldarg.0
0x99073  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x99078  ldstr    aLogicalanddisp// "_logicalAndDisplayNamesMapping"
0x9907d  ldarg.0
0x9907e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::logicalAndDisplayNamesMapping
0x99083  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x99088  ldarg.0
0x99089  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9908e  ldstr    aExternalpartye_0// "_externalPartyEnabledEntityDisplayNames"
0x99093  ldarg.0
0x99094  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::externalPartyEnabledEntityDisplayNames
0x99099  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x9909e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVarArray(string, class [mscorlib]System.Collections.IEnumerable)
0x990a3  ldarg.0
0x990a4  ldc.i4.1
0x990a5  call     instance void Microsoft.Crm.Web.Tools.SystemSettings.AutoCreateExternalPartyEnabledConfiguration::EnableButtons(bool enable)
0x990aa  ret
```
