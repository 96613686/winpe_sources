# Microsoft.Crm.Web.Tools.SystemSettings.QuickFindConfiguration::ConfigureHeader

- ea: `0x96a70`
- end: `0x96df4`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.QuickFindConfiguration::ConfigureHeader`
- size: `900`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x96a70`
- `0x96f90`
- `0x97440`
- `0x974e0`
- `0x97500`

## string_xrefs

- `0x96a8c`: `/_common/styles/dialogs.css.aspx`
- `0x96bd2`: `Button_Label_Remove`
- `0x96c2d`: `Web._controls.listedit.buttons.MoveUp`
- `0x96c88`: `Web._controls.listedit.buttons.MoveDown`
- `0x96a7c`: `/_common/styles/global.css.aspx`
- `0x96abc`: `/Tools/SystemSettings/Dialogs/QuickFindConfiguration.css.aspx`
- `0x96ad7`: `/_static/tools/systemcustomization/scripts/quickfindconfig.js`
- `0x96afe`: `SystemCustomization.QuickFindConfiguration.AvailableEntitiesText`
- `0x96b19`: `SystemCustomization.QuickFindConfiguration.SelectedEntitiesText`
- `0x96b41`: `SystemCustomization.QuickFindConfiguration.Note`
- `0x96b5c`: `SystemCustomization.QuickFindConfiguration.NoteForCategorizedSearchText`
- `0x96b92`: `SystemCustomization.QuickFindConfiguration.AddButtonText`
- `0x96bb2`: `SystemCustomization.QuickFindConfiguration.AddButtonText`
- `0x96bed`: `SystemCustomization.QuickFindConfiguration.RemoveButtonText`
- `0x96c0d`: `SystemCustomization.QuickFindConfiguration.RemoveButtonText`
- `0x96c48`: `SystemCustomization.QuickFindConfiguration.MoveUp`
- `0x96c68`: `SystemCustomization.QuickFindConfiguration.MoveUp`
- `0x96ca3`: `SystemCustomization.QuickFindConfiguration.MoveDown`
- `0x96cc3`: `SystemCustomization.QuickFindConfiguration.MoveDown`
- `0x96d08`: `SystemCustomization.QuickFindConfiguration.MustSelectEntityWarning`
- `0x96d28`: `SystemCustomization.QuickFindConfiguration.MustContainOneEntity`
- `0x96d4d`: `SystemCustomization.QuickFindConfiguration.MaxNumberOfEntitiesReached`

## pseudocode

```c

```

## disassembly

```asm
0x96a70  ldarg.0
0x96a71  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0x96a76  ldarg.0
0x96a77  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96a7c  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0x96a81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x96a86  ldarg.0
0x96a87  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96a8c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x96a91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x96a96  ldarg.0
0x96a97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96a9c  ldstr    aControlsNaviga// "/_controls/navigation/map.css.aspx"
0x96aa1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x96aa6  ldarg.0
0x96aa7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96aac  ldstr    aStaticMobileSt// "/_static/mobile/styles/console/global.c"...
0x96ab1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x96ab6  ldarg.0
0x96ab7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96abc  ldstr    aToolsSystemset_0// "/Tools/SystemSettings/Dialogs/QuickFind"...
0x96ac1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x96ac6  ldarg.0
0x96ac7  call     instance bool Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::CheckReadPrivilege()
0x96acc  brfalse  loc_96DB8
0x96ad1  ldarg.0
0x96ad2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96ad7  ldstr    aStaticToolsSys_3// "/_static/tools/systemcustomization/scri"...
0x96adc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x96ae1  ldarg.0
0x96ae2  ldarg.0
0x96ae3  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::get_OrgContext()
0x96ae8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x96aed  call     instance void Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::UpdateEntityLimitSetting(valuetype [mscorlib]System.Guid organizationId)
0x96af2  ldarg.0
0x96af3  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::AvailableEntitiesText
0x96af8  ldarg.0
0x96af9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96afe  ldstr    aSystemcustomiz_222// "SystemCustomization.QuickFindConfigurat"...
0x96b03  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96b08  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x96b0d  ldarg.0
0x96b0e  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::SelectedEntitiesText
0x96b13  ldarg.0
0x96b14  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96b19  ldstr    aSystemcustomiz_223// "SystemCustomization.QuickFindConfigurat"...
0x96b1e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96b23  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x96b28  ldarg.0
0x96b29  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_orgContext
0x96b2e  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.ElasticSearchIndexUtility::IsElasticSearchEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x96b33  brfalse.s loc_96B6B
0x96b35  ldarg.0
0x96b36  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.QuickFindConfiguration::NoteString
0x96b3b  ldarg.0
0x96b3c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96b41  ldstr    aSystemcustomiz_224// "SystemCustomization.QuickFindConfigurat"...
0x96b46  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96b4b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x96b50  ldarg.0
0x96b51  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.QuickFindConfiguration::NoteForCategorizedSearchText
0x96b56  ldarg.0
0x96b57  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96b5c  ldstr    aSystemcustomiz_225// "SystemCustomization.QuickFindConfigurat"...
0x96b61  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96b66  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x96b6b  ldarg.0
0x96b6c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::AddButton
0x96b71  ldarg.0
0x96b72  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96b77  ldstr    aMenuLabelAdd// "Menu_Label_Add"
0x96b7c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96b81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x96b86  ldarg.0
0x96b87  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::AddButton
0x96b8c  ldarg.0
0x96b8d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96b92  ldstr    aSystemcustomiz_226// "SystemCustomization.QuickFindConfigurat"...
0x96b97  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96b9c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x96ba1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x96ba6  ldarg.0
0x96ba7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::AddButton
0x96bac  ldarg.0
0x96bad  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96bb2  ldstr    aSystemcustomiz_226// "SystemCustomization.QuickFindConfigurat"...
0x96bb7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96bbc  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x96bc1  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x96bc6  ldarg.0
0x96bc7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::RemoveButton
0x96bcc  ldarg.0
0x96bcd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96bd2  ldstr    aButtonLabelRem// "Button_Label_Remove"
0x96bd7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96bdc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x96be1  ldarg.0
0x96be2  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::RemoveButton
0x96be7  ldarg.0
0x96be8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96bed  ldstr    aSystemcustomiz_227// "SystemCustomization.QuickFindConfigurat"...
0x96bf2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96bf7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x96bfc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x96c01  ldarg.0
0x96c02  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::RemoveButton
0x96c07  ldarg.0
0x96c08  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96c0d  ldstr    aSystemcustomiz_227// "SystemCustomization.QuickFindConfigurat"...
0x96c12  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96c17  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x96c1c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x96c21  ldarg.0
0x96c22  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.QuickFindConfiguration::MoveUpButton
0x96c27  ldarg.0
0x96c28  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96c2d  ldstr    aWebControlsLis// "Web._controls.listedit.buttons.MoveUp"
0x96c32  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96c37  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x96c3c  ldarg.0
0x96c3d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.QuickFindConfiguration::MoveUpButton
0x96c42  ldarg.0
0x96c43  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96c48  ldstr    aSystemcustomiz_228// "SystemCustomization.QuickFindConfigurat"...
0x96c4d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96c52  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x96c57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x96c5c  ldarg.0
0x96c5d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.QuickFindConfiguration::MoveUpButton
0x96c62  ldarg.0
0x96c63  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96c68  ldstr    aSystemcustomiz_228// "SystemCustomization.QuickFindConfigurat"...
0x96c6d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96c72  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x96c77  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x96c7c  ldarg.0
0x96c7d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.QuickFindConfiguration::MoveDownButton
0x96c82  ldarg.0
0x96c83  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96c88  ldstr    aWebControlsLis_0// "Web._controls.listedit.buttons.MoveDown"
0x96c8d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96c92  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x96c97  ldarg.0
0x96c98  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.QuickFindConfiguration::MoveDownButton
0x96c9d  ldarg.0
0x96c9e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96ca3  ldstr    aSystemcustomiz_229// "SystemCustomization.QuickFindConfigurat"...
0x96ca8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96cad  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x96cb2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x96cb7  ldarg.0
0x96cb8  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.QuickFindConfiguration::MoveDownButton
0x96cbd  ldarg.0
0x96cbe  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96cc3  ldstr    aSystemcustomiz_229// "SystemCustomization.QuickFindConfigurat"...
0x96cc8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96ccd  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x96cd2  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x96cd7  ldarg.0
0x96cd8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96cdd  ldstr    aLocidFormsSave// "LOCID_FORMS_SAVE_CONFIRM_TITLE"
0x96ce2  ldarg.0
0x96ce3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96ce8  ldstr    aWebFormsStyles_2// "Web._forms.styles.FORM.crm.htc_Title"
0x96ced  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96cf2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x96cf7  ldarg.0
0x96cf8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96cfd  ldstr    aLocidMustSelec// "LOCID_MUST_SELECT_ENTITY_WARNING"
0x96d02  ldarg.0
0x96d03  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96d08  ldstr    aSystemcustomiz_230// "SystemCustomization.QuickFindConfigurat"...
0x96d0d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96d12  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x96d17  ldarg.0
0x96d18  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96d1d  ldstr    aLocidMustConta// "LOCID_MUST_CONTAIN_ONE_ENTITY_WARNING"
0x96d22  ldarg.0
0x96d23  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96d28  ldstr    aSystemcustomiz_231// "SystemCustomization.QuickFindConfigurat"...
0x96d2d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96d32  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x96d37  ldarg.0
0x96d38  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96d3d  ldstr    aLocidReachMaxE// "LOCID_REACH_MAX_ENTITIES_WARNING"
0x96d42  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x96d47  ldarg.0
0x96d48  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96d4d  ldstr    aSystemcustomiz_232// "SystemCustomization.QuickFindConfigurat"...
0x96d52  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96d57  ldc.i4.1
0x96d58  newarr   [mscorlib]System.Object
0x96d5d  dup
0x96d5e  ldc.i4.0
0x96d5f  ldarg.0
0x96d60  ldfld    int32 Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_maxNumberOfEntitiesAllowed
0x96d65  box      [mscorlib]System.Int32
0x96d6a  stelem.ref
0x96d6b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x96d70  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x96d75  ldarg.0
0x96d76  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96d7b  ldstr    aMaxEntitiesAll// "MAX_ENTITIES_ALLOWED"
0x96d80  ldarg.0
0x96d81  ldfld    int32 Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_maxNumberOfEntitiesAllowed
0x96d86  conv.i8
0x96d87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x96d8c  ldarg.0
0x96d8d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96d92  ldstr    aIsRelevanceSea// "IS_RELEVANCE_SEARCH"
0x96d97  ldc.i4.0
0x96d98  conv.i8
0x96d99  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x96d9e  ldarg.0
0x96d9f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x96da4  ldstr    aSoftFieldLimit// "SOFT_FIELD_LIMIT_FOR_RELEVANCE_SEARCH"
0x96da9  ldc.i4.0
0x96daa  conv.i8
0x96dab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x96db0  ldarg.0
0x96db1  ldc.i4.1
0x96db2  callvirt instance void Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::EnableButtons(bool enable)
0x96db7  ret
0x96db8  ldarg.0
0x96db9  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::Lists
0x96dbe  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x96dc3  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Clear()
0x96dc8  ldarg.0
0x96dc9  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::Lists
0x96dce  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x96dd3  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Clear()
0x96dd8  ldarg.0
0x96dd9  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::PageHeader
0x96dde  ldarg.0
0x96ddf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x96de4  ldstr    aErrorMessage0x// "Error_Message_0x80070005"
0x96de9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x96dee  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x96df3  ret
```
