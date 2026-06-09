# Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchFacetsAndFiltersConfiguration::ConfigureHeader

- ea: `0x97e40`
- end: `0x98222`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchFacetsAndFiltersConfiguration::ConfigureHeader`
- size: `994`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x96f90`
- `0x97440`
- `0x974e0`
- `0x97500`
- `0x97e40`

## string_xrefs

- `0x97e5c`: `/_common/styles/dialogs.css.aspx`
- `0x97f8a`: `Button_Label_Remove`
- `0x97fe5`: `Web._controls.listedit.buttons.MoveUp`
- `0x98040`: `Web._controls.listedit.buttons.MoveDown`
- `0x97e4c`: `/_common/styles/global.css.aspx`
- `0x97e8c`: `/Tools/SystemSettings/Dialogs/QuickFindConfiguration.css.aspx`
- `0x9811b`: `SystemCustomization.QuickFindConfiguration.MustSelectEntityWarning`
- `0x9813b`: `SystemCustomization.QuickFindConfiguration.MustContainOneEntity`
- `0x98160`: `SystemCustomization.QuickFindConfiguration.MaxNumberOfEntitiesReached`
- `0x97e9c`: `/Tools/SystemSettings/Dialogs/RelevanceSearchConfiguration.css.aspx`
- `0x97fa5`: `ExternalSearch_Customization_Entity_Remove_Label`
- `0x97fc5`: `ExternalSearch_Customization_Entity_Remove_Label`
- `0x98000`: `ExternalSearch_Customization_Entity_MoveUp_Label`
- `0x98020`: `ExternalSearch_Customization_Entity_MoveUp_Label`
- `0x9805b`: `ExternalSearch_Customization_Entity_MoveDown_Label`
- `0x9807b`: `ExternalSearch_Customization_Entity_MoveDown_Label`

## pseudocode

```c

```

## disassembly

```asm
0x97e40  ldarg.0
0x97e41  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0x97e46  ldarg.0
0x97e47  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97e4c  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0x97e51  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x97e56  ldarg.0
0x97e57  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97e5c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x97e61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x97e66  ldarg.0
0x97e67  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97e6c  ldstr    aControlsNaviga// "/_controls/navigation/map.css.aspx"
0x97e71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x97e76  ldarg.0
0x97e77  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97e7c  ldstr    aStaticMobileSt// "/_static/mobile/styles/console/global.c"...
0x97e81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x97e86  ldarg.0
0x97e87  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97e8c  ldstr    aToolsSystemset_0// "/Tools/SystemSettings/Dialogs/QuickFind"...
0x97e91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x97e96  ldarg.0
0x97e97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97e9c  ldstr    aToolsSystemset_2// "/Tools/SystemSettings/Dialogs/Relevance"...
0x97ea1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x97ea6  ldarg.0
0x97ea7  call     instance bool Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::CheckReadPrivilege()
0x97eac  brfalse  loc_981E6
0x97eb1  ldarg.0
0x97eb2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97eb7  ldstr    aStaticToolsSys_4// "/_static/tools/systemcustomization/scri"...
0x97ebc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x97ec1  ldarg.0
0x97ec2  ldarg.0
0x97ec3  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::get_OrgContext()
0x97ec8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x97ecd  call     instance void Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::UpdateEntityLimitSetting(valuetype [mscorlib]System.Guid organizationId)
0x97ed2  ldarg.0
0x97ed3  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::AvailableEntitiesText
0x97ed8  ldarg.0
0x97ed9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97ede  ldstr    aExternalsearch_6// "ExternalSearch_Customization_Entity_Ava"...
0x97ee3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97ee8  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x97eed  ldarg.0
0x97eee  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::SelectedEntitiesText
0x97ef3  ldarg.0
0x97ef4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97ef9  ldstr    aExternalsearch_7// "ExternalSearch_Customization_Entity_Sel"...
0x97efe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97f03  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x97f08  ldarg.0
0x97f09  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchFacetsAndFiltersConfiguration::FilterEntityComboText
0x97f0e  ldarg.0
0x97f0f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97f14  ldstr    aExternalsearch_8// "ExternalSearch_Customization_Entity_Dro"...
0x97f19  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97f1e  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x97f23  ldarg.0
0x97f24  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::AddButton
0x97f29  ldarg.0
0x97f2a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97f2f  ldstr    aMenuLabelAdd// "Menu_Label_Add"
0x97f34  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97f39  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x97f3e  ldarg.0
0x97f3f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::AddButton
0x97f44  ldarg.0
0x97f45  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97f4a  ldstr    aExternalsearch_9// "ExternalSearch_Customization_Entity_Add"...
0x97f4f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97f54  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x97f59  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x97f5e  ldarg.0
0x97f5f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::AddButton
0x97f64  ldarg.0
0x97f65  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97f6a  ldstr    aExternalsearch_9// "ExternalSearch_Customization_Entity_Add"...
0x97f6f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97f74  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x97f79  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x97f7e  ldarg.0
0x97f7f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::RemoveButton
0x97f84  ldarg.0
0x97f85  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97f8a  ldstr    aButtonLabelRem// "Button_Label_Remove"
0x97f8f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97f94  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x97f99  ldarg.0
0x97f9a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::RemoveButton
0x97f9f  ldarg.0
0x97fa0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97fa5  ldstr    aExternalsearch_10// "ExternalSearch_Customization_Entity_Rem"...
0x97faa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97faf  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x97fb4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x97fb9  ldarg.0
0x97fba  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::RemoveButton
0x97fbf  ldarg.0
0x97fc0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97fc5  ldstr    aExternalsearch_10// "ExternalSearch_Customization_Entity_Rem"...
0x97fca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97fcf  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x97fd4  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x97fd9  ldarg.0
0x97fda  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchFacetsAndFiltersConfiguration::MoveUpButton
0x97fdf  ldarg.0
0x97fe0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97fe5  ldstr    aWebControlsLis// "Web._controls.listedit.buttons.MoveUp"
0x97fea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97fef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x97ff4  ldarg.0
0x97ff5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchFacetsAndFiltersConfiguration::MoveUpButton
0x97ffa  ldarg.0
0x97ffb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98000  ldstr    aExternalsearch_11// "ExternalSearch_Customization_Entity_Mov"...
0x98005  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9800a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x9800f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x98014  ldarg.0
0x98015  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchFacetsAndFiltersConfiguration::MoveUpButton
0x9801a  ldarg.0
0x9801b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98020  ldstr    aExternalsearch_11// "ExternalSearch_Customization_Entity_Mov"...
0x98025  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9802a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x9802f  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x98034  ldarg.0
0x98035  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchFacetsAndFiltersConfiguration::MoveDownButton
0x9803a  ldarg.0
0x9803b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98040  ldstr    aWebControlsLis_0// "Web._controls.listedit.buttons.MoveDown"
0x98045  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9804a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x9804f  ldarg.0
0x98050  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchFacetsAndFiltersConfiguration::MoveDownButton
0x98055  ldarg.0
0x98056  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9805b  ldstr    aExternalsearch_12// "ExternalSearch_Customization_Entity_Mov"...
0x98060  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98065  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x9806a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x9806f  ldarg.0
0x98070  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchFacetsAndFiltersConfiguration::MoveDownButton
0x98075  ldarg.0
0x98076  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9807b  ldstr    aExternalsearch_12// "ExternalSearch_Customization_Entity_Mov"...
0x98080  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98085  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x9808a  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x9808f  ldarg.0
0x98090  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchFacetsAndFiltersConfiguration::DefaultButton
0x98095  ldarg.0
0x98096  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9809b  ldstr    aExternalsearch_13// "ExternalSearch_Customization_Entity_Def"...
0x980a0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x980a5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x980aa  ldarg.0
0x980ab  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchFacetsAndFiltersConfiguration::DefaultButton
0x980b0  ldarg.0
0x980b1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x980b6  ldstr    aExternalsearch_13// "ExternalSearch_Customization_Entity_Def"...
0x980bb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x980c0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x980c5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x980ca  ldarg.0
0x980cb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchFacetsAndFiltersConfiguration::DefaultButton
0x980d0  ldarg.0
0x980d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x980d6  ldstr    aExternalsearch_13// "ExternalSearch_Customization_Entity_Def"...
0x980db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x980e0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x980e5  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x980ea  ldarg.0
0x980eb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x980f0  ldstr    aLocidFormsSave// "LOCID_FORMS_SAVE_CONFIRM_TITLE"
0x980f5  ldarg.0
0x980f6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x980fb  ldstr    aWebFormsStyles_2// "Web._forms.styles.FORM.crm.htc_Title"
0x98100  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98105  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x9810a  ldarg.0
0x9810b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98110  ldstr    aLocidMustSelec// "LOCID_MUST_SELECT_ENTITY_WARNING"
0x98115  ldarg.0
0x98116  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9811b  ldstr    aSystemcustomiz_230// "SystemCustomization.QuickFindConfigurat"...
0x98120  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98125  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x9812a  ldarg.0
0x9812b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98130  ldstr    aLocidMustConta// "LOCID_MUST_CONTAIN_ONE_ENTITY_WARNING"
0x98135  ldarg.0
0x98136  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9813b  ldstr    aSystemcustomiz_231// "SystemCustomization.QuickFindConfigurat"...
0x98140  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x98145  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x9814a  ldarg.0
0x9814b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x98150  ldstr    aLocidReachMaxE// "LOCID_REACH_MAX_ENTITIES_WARNING"
0x98155  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x9815a  ldarg.0
0x9815b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98160  ldstr    aSystemcustomiz_232// "SystemCustomization.QuickFindConfigurat"...
0x98165  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9816a  ldc.i4.1
0x9816b  newarr   [mscorlib]System.Object
0x98170  dup
0x98171  ldc.i4.0
0x98172  ldarg.0
0x98173  ldfld    int32 Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_maxNumberOfEntitiesAllowed
0x98178  box      [mscorlib]System.Int32
0x9817d  stelem.ref
0x9817e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x98183  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x98188  ldarg.0
0x98189  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9818e  ldstr    aMaxEntitiesAll// "MAX_ENTITIES_ALLOWED"
0x98193  ldarg.0
0x98194  ldfld    int32 Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_maxNumberOfEntitiesAllowed
0x98199  conv.i8
0x9819a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x9819f  ldarg.0
0x981a0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x981a5  ldstr    aIsRelevanceSea// "IS_RELEVANCE_SEARCH"
0x981aa  ldc.i4.1
0x981ab  conv.i8
0x981ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x981b1  ldarg.0
0x981b2  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::get_OrgContext()
0x981b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x981bc  ldstr    aSoftfieldlimit// "SoftFieldLimitForRelevanceSearch"
0x981c1  ldc.i4   0x3E8
0x981c6  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.ElasticSearchIndexUtility::GetSettingFromOrganizationThenDeployment(valuetype [mscorlib]System.Guid, string, int32)
0x981cb  stloc.0
0x981cc  ldarg.0
0x981cd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x981d2  ldstr    aSoftFieldLimit// "SOFT_FIELD_LIMIT_FOR_RELEVANCE_SEARCH"
0x981d7  ldloc.0
0x981d8  conv.i8
0x981d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x981de  ldarg.0
0x981df  ldc.i4.1
0x981e0  callvirt instance void Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::EnableButtons(bool enable)
0x981e5  ret
0x981e6  ldarg.0
0x981e7  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::Lists
0x981ec  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x981f1  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Clear()
0x981f6  ldarg.0
0x981f7  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::Lists
0x981fc  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x98201  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Clear()
0x98206  ldarg.0
0x98207  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::PageHeader
0x9820c  ldarg.0
0x9820d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x98212  ldstr    aErrorMessage0x// "Error_Message_0x80070005"
0x98217  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9821c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x98221  ret
```
