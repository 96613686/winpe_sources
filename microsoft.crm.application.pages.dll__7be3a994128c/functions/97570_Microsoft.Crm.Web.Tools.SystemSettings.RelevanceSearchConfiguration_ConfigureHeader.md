# Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchConfiguration::ConfigureHeader

- ea: `0x97570`
- end: `0x97846`
- name: `Microsoft.Crm.Web.Tools.SystemSettings.RelevanceSearchConfiguration::ConfigureHeader`
- size: `726`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x96f90`
- `0x97440`
- `0x974e0`
- `0x97500`
- `0x97570`

## string_xrefs

- `0x9758c`: `/_common/styles/dialogs.css.aspx`
- `0x9769f`: `Button_Label_Remove`
- `0x9757c`: `/_common/styles/global.css.aspx`
- `0x975bc`: `/Tools/SystemSettings/Dialogs/QuickFindConfiguration.css.aspx`
- `0x975e7`: `/_static/tools/systemcustomization/scripts/quickfindconfig.js`
- `0x9760e`: `SystemCustomization.QuickFindConfiguration.AvailableEntitiesText`
- `0x97629`: `SystemCustomization.QuickFindConfiguration.SelectedEntitiesText`
- `0x9765f`: `SystemCustomization.QuickFindConfiguration.AddButtonText`
- `0x9767f`: `SystemCustomization.QuickFindConfiguration.AddButtonText`
- `0x976ba`: `SystemCustomization.QuickFindConfiguration.RemoveButtonText`
- `0x976da`: `SystemCustomization.QuickFindConfiguration.RemoveButtonText`
- `0x9771f`: `SystemCustomization.QuickFindConfiguration.MustSelectEntityWarning`
- `0x9773f`: `SystemCustomization.QuickFindConfiguration.MustContainOneEntity`
- `0x97764`: `SystemCustomization.QuickFindConfiguration.MaxNumberOfEntitiesReached`
- `0x975cc`: `/Tools/SystemSettings/Dialogs/RelevanceSearchConfiguration.css.aspx`
- `0x977b4`: `SystemCustomization.RelevanceSearchConfiguration.ProgressBarStatus`

## pseudocode

```c

```

## disassembly

```asm
0x97570  ldarg.0
0x97571  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0x97576  ldarg.0
0x97577  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9757c  ldstr    aCommonStylesGl// "/_common/styles/global.css.aspx"
0x97581  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x97586  ldarg.0
0x97587  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9758c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x97591  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x97596  ldarg.0
0x97597  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x9759c  ldstr    aControlsNaviga// "/_controls/navigation/map.css.aspx"
0x975a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x975a6  ldarg.0
0x975a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x975ac  ldstr    aStaticMobileSt// "/_static/mobile/styles/console/global.c"...
0x975b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x975b6  ldarg.0
0x975b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x975bc  ldstr    aToolsSystemset_0// "/Tools/SystemSettings/Dialogs/QuickFind"...
0x975c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x975c6  ldarg.0
0x975c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x975cc  ldstr    aToolsSystemset_2// "/Tools/SystemSettings/Dialogs/Relevance"...
0x975d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x975d6  ldarg.0
0x975d7  call     instance bool Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::CheckReadPrivilege()
0x975dc  brfalse  loc_9780A
0x975e1  ldarg.0
0x975e2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x975e7  ldstr    aStaticToolsSys_3// "/_static/tools/systemcustomization/scri"...
0x975ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x975f1  ldarg.0
0x975f2  ldarg.0
0x975f3  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::get_OrgContext()
0x975f8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x975fd  call     instance void Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::UpdateEntityLimitSetting(valuetype [mscorlib]System.Guid organizationId)
0x97602  ldarg.0
0x97603  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::AvailableEntitiesText
0x97608  ldarg.0
0x97609  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9760e  ldstr    aSystemcustomiz_222// "SystemCustomization.QuickFindConfigurat"...
0x97613  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97618  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x9761d  ldarg.0
0x9761e  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::SelectedEntitiesText
0x97623  ldarg.0
0x97624  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97629  ldstr    aSystemcustomiz_223// "SystemCustomization.QuickFindConfigurat"...
0x9762e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97633  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x97638  ldarg.0
0x97639  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::AddButton
0x9763e  ldarg.0
0x9763f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97644  ldstr    aMenuLabelAdd// "Menu_Label_Add"
0x97649  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9764e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x97653  ldarg.0
0x97654  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::AddButton
0x97659  ldarg.0
0x9765a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9765f  ldstr    aSystemcustomiz_226// "SystemCustomization.QuickFindConfigurat"...
0x97664  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97669  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x9766e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x97673  ldarg.0
0x97674  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::AddButton
0x97679  ldarg.0
0x9767a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9767f  ldstr    aSystemcustomiz_226// "SystemCustomization.QuickFindConfigurat"...
0x97684  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97689  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x9768e  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x97693  ldarg.0
0x97694  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::RemoveButton
0x97699  ldarg.0
0x9769a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9769f  ldstr    aButtonLabelRem// "Button_Label_Remove"
0x976a4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x976a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x976ae  ldarg.0
0x976af  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::RemoveButton
0x976b4  ldarg.0
0x976b5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x976ba  ldstr    aSystemcustomiz_227// "SystemCustomization.QuickFindConfigurat"...
0x976bf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x976c4  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x976c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x976ce  ldarg.0
0x976cf  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::RemoveButton
0x976d4  ldarg.0
0x976d5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x976da  ldstr    aSystemcustomiz_227// "SystemCustomization.QuickFindConfigurat"...
0x976df  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x976e4  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x976e9  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x976ee  ldarg.0
0x976ef  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x976f4  ldstr    aLocidFormsSave// "LOCID_FORMS_SAVE_CONFIRM_TITLE"
0x976f9  ldarg.0
0x976fa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x976ff  ldstr    aWebFormsStyles_2// "Web._forms.styles.FORM.crm.htc_Title"
0x97704  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97709  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x9770e  ldarg.0
0x9770f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97714  ldstr    aLocidMustSelec// "LOCID_MUST_SELECT_ENTITY_WARNING"
0x97719  ldarg.0
0x9771a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9771f  ldstr    aSystemcustomiz_230// "SystemCustomization.QuickFindConfigurat"...
0x97724  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97729  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x9772e  ldarg.0
0x9772f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97734  ldstr    aLocidMustConta// "LOCID_MUST_CONTAIN_ONE_ENTITY_WARNING"
0x97739  ldarg.0
0x9773a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x9773f  ldstr    aSystemcustomiz_231// "SystemCustomization.QuickFindConfigurat"...
0x97744  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97749  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x9774e  ldarg.0
0x9774f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97754  ldstr    aLocidReachMaxE// "LOCID_REACH_MAX_ENTITIES_WARNING"
0x97759  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x9775e  ldarg.0
0x9775f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97764  ldstr    aSystemcustomiz_232// "SystemCustomization.QuickFindConfigurat"...
0x97769  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9776e  ldc.i4.1
0x9776f  newarr   [mscorlib]System.Object
0x97774  dup
0x97775  ldc.i4.0
0x97776  ldarg.0
0x97777  ldfld    int32 Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_maxNumberOfEntitiesAllowed
0x9777c  box      [mscorlib]System.Int32
0x97781  stelem.ref
0x97782  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x97787  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x9778c  ldarg.0
0x9778d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x97792  ldstr    aMaxEntitiesAll// "MAX_ENTITIES_ALLOWED"
0x97797  ldarg.0
0x97798  ldfld    int32 Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::_maxNumberOfEntitiesAllowed
0x9779d  conv.i8
0x9779e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x977a3  ldarg.0
0x977a4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x977a9  ldstr    aProgressBarSta// "PROGRESS_BAR_STATUS_FORMAT"
0x977ae  ldarg.0
0x977af  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x977b4  ldstr    aSystemcustomiz_236// "SystemCustomization.RelevanceSearchConf"...
0x977b9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x977be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x977c3  ldarg.0
0x977c4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x977c9  ldstr    aIsRelevanceSea// "IS_RELEVANCE_SEARCH"
0x977ce  ldc.i4.1
0x977cf  conv.i8
0x977d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x977d5  ldarg.0
0x977d6  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::get_OrgContext()
0x977db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x977e0  ldstr    aSoftfieldlimit// "SoftFieldLimitForRelevanceSearch"
0x977e5  ldc.i4   0x3E8
0x977ea  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.ElasticSearchIndexUtility::GetSettingFromOrganizationThenDeployment(valuetype [mscorlib]System.Guid, string, int32)
0x977ef  stloc.0
0x977f0  ldarg.0
0x977f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x977f6  ldstr    aSoftFieldLimit// "SOFT_FIELD_LIMIT_FOR_RELEVANCE_SEARCH"
0x977fb  ldloc.0
0x977fc  conv.i8
0x977fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x97802  ldarg.0
0x97803  ldc.i4.1
0x97804  callvirt instance void Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::EnableButtons(bool enable)
0x97809  ret
0x9780a  ldarg.0
0x9780b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::Lists
0x97810  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x97815  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Clear()
0x9781a  ldarg.0
0x9781b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::Lists
0x97820  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x97825  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Clear()
0x9782a  ldarg.0
0x9782b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Web.Tools.SystemSettings.SearchConfiguration::PageHeader
0x97830  ldarg.0
0x97831  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x97836  ldstr    aErrorMessage0x// "Error_Message_0x80070005"
0x9783b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x97840  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x97845  ret
```
