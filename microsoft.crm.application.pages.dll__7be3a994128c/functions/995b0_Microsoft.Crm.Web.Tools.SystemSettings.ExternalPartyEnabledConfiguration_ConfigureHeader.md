# Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::ConfigureHeader

- ea: `0x995b0`
- end: `0x9979b`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::ConfigureHeader`
- size: `491`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x99d60`

## string_xrefs

- `0x995cc`: `/_common/styles/dialogs.css.aspx`
- `0x996b3`: `Button_Label_Remove`
- `0x995bc`: `/_common/styles/global.css.aspx`
- `0x995fc`: `/Tools/SystemSettings/Dialogs/ExternalPartyEnabledConfiguration.css.aspx`
- `0x996ce`: `External_Applications_Setup_RemoveButtonText`
- `0x996ee`: `External_Applications_Setup_RemoveButtonText`
- `0x9960c`: `/_static/tools/systemcustomization/scripts/externalpartyenabledconfig.js`

## pseudocode

```c

```

## disassembly

```asm
0x995b0  ldarg.0
0x995b1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0x995b6  ldarg.0
0x995b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x995bc  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0x995c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x995c6  ldarg.0
0x995c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x995cc  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x995d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x995d6  ldarg.0
0x995d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x995dc  ldstr    aControlsNaviga// "/_controls/navigation/map.css.aspx"
0x995e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x995e6  ldarg.0
0x995e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x995ec  ldstr    aStaticMobileSt// "/_static/mobile/styles/console/global.c"...
0x995f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x995f6  ldarg.0
0x995f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x995fc  ldstr    aToolsSystemset_5// "/Tools/SystemSettings/Dialogs/ExternalP"...
0x99601  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x99606  ldarg.0
0x99607  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9960c  ldstr    aStaticToolsSys_6// "/_static/tools/systemcustomization/scri"...
0x99611  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x99616  ldarg.0
0x99617  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::AvailableEntitiesText
0x9961c  ldarg.0
0x9961d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x99622  ldstr    aExternalApplic_0// "External_Applications_Setup_AvailableEn"...
0x99627  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9962c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x99631  ldarg.0
0x99632  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::SelectedEntitiesText
0x99637  ldarg.0
0x99638  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9963d  ldstr    aExternalApplic_1// "External_Applications_Setup_SelectedEnt"...
0x99642  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99647  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x9964c  ldarg.0
0x9964d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::AddButton
0x99652  ldarg.0
0x99653  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x99658  ldstr    aMenuLabelAdd// "Menu_Label_Add"
0x9965d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99662  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x99667  ldarg.0
0x99668  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::AddButton
0x9966d  ldarg.0
0x9966e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x99673  ldstr    aExternalApplic_2// "External_Applications_Setup_AddButtonTe"...
0x99678  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9967d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x99682  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x99687  ldarg.0
0x99688  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::AddButton
0x9968d  ldarg.0
0x9968e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x99693  ldstr    aExternalApplic_2// "External_Applications_Setup_AddButtonTe"...
0x99698  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9969d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x996a2  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x996a7  ldarg.0
0x996a8  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::RemoveButton
0x996ad  ldarg.0
0x996ae  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x996b3  ldstr    aButtonLabelRem// "Button_Label_Remove"
0x996b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x996bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x996c2  ldarg.0
0x996c3  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::RemoveButton
0x996c8  ldarg.0
0x996c9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x996ce  ldstr    aExternalApplic_3// "External_Applications_Setup_RemoveButto"...
0x996d3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x996d8  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x996dd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x996e2  ldarg.0
0x996e3  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::RemoveButton
0x996e8  ldarg.0
0x996e9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x996ee  ldstr    aExternalApplic_3// "External_Applications_Setup_RemoveButto"...
0x996f3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x996f8  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x996fd  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x99702  ldarg.0
0x99703  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x99708  ldstr    aLocidFormsSave// "LOCID_FORMS_SAVE_CONFIRM_TITLE"
0x9970d  ldarg.0
0x9970e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x99713  ldstr    aWebFormsStyles_2// "Web._forms.styles.FORM.crm.htc_Title"
0x99718  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9971d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x99722  ldarg.0
0x99723  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x99728  ldstr    aLocidMustSelec// "LOCID_MUST_SELECT_ENTITY_WARNING"
0x9972d  ldarg.0
0x9972e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x99733  ldstr    aExternalApplic_7// "External_Applications_Setup_MustSelectE"...
0x99738  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9973d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x99742  ldarg.0
0x99743  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x99748  ldstr    aLocidMustConta// "LOCID_MUST_CONTAIN_ONE_ENTITY_WARNING"
0x9974d  ldarg.0
0x9974e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x99753  ldstr    aExternalApplic_4// "External_Applications_Setup_MustContain"...
0x99758  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9975d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x99762  ldarg.0
0x99763  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x99768  ldstr    aLogicalanddisp// "_logicalAndDisplayNamesMapping"
0x9976d  ldarg.0
0x9976e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::logicalAndDisplayNamesMapping
0x99773  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>)
0x99778  ldarg.0
0x99779  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9977e  ldstr    aExternalpartye_0// "_externalPartyEnabledEntityDisplayNames"
0x99783  ldarg.0
0x99784  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::externalPartyEnabledEntityDisplayNames
0x99789  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x9978e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVarArray(string, class [mscorlib]System.Collections.IEnumerable)
0x99793  ldarg.0
0x99794  ldc.i4.1
0x99795  call     instance void Microsoft.Crm.Web.Tools.SystemSettings.ExternalPartyEnabledConfiguration::EnableButtons(bool enable)
0x9979a  ret
```
