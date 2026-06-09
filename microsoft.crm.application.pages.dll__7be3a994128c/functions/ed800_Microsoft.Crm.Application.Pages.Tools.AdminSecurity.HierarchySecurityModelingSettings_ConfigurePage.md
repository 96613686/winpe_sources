# Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::ConfigurePage

- ea: `0xed800`
- end: `0xeda33`
- name: `Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::ConfigurePage`
- size: `563`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0xed800`
- `0xedac0`
- `0xede20`
- `0xee0b0`
- `0xee270`

## string_xrefs

- `0xed8dd`: `Button_Label_Remove`
- `0xed9a6`: `SystemCustomization.QuickFindConfiguration.MustSelectEntityWarning`
- `0xed80c`: `AdminSecurity.PageHeader`
- `0xed82c`: `AdminSecurity.PageDescription`
- `0xed84c`: `AdminSecurity.AvailableEntitiesText`
- `0xed867`: `AdminSecurity.SelectedEntitiesText`
- `0xed89d`: `AdminSecurity.AddButtonText`
- `0xed8bd`: `AdminSecurity.AddButtonText`
- `0xed8f8`: `AdminSecurity.RemoveButtonText`
- `0xed918`: `AdminSecurity.RemoveButtonText`
- `0xed95b`: `HierarchySecuritySettings.MaxDepthError_Blank`

## pseudocode

```c

```

## disassembly

```asm
0xed800  ldarg.0
0xed801  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::PageHeader
0xed806  ldarg.0
0xed807  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed80c  ldstr    aAdminsecurityP// "AdminSecurity.PageHeader"
0xed811  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed816  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xed81b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0xed820  ldarg.0
0xed821  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::PageDescription
0xed826  ldarg.0
0xed827  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed82c  ldstr    aAdminsecurityP_0// "AdminSecurity.PageDescription"
0xed831  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed836  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xed83b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0xed840  ldarg.0
0xed841  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::AvailableEntitiesText
0xed846  ldarg.0
0xed847  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed84c  ldstr    aAdminsecurityA_0// "AdminSecurity.AvailableEntitiesText"
0xed851  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed856  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xed85b  ldarg.0
0xed85c  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::SelectedEntitiesText
0xed861  ldarg.0
0xed862  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed867  ldstr    aAdminsecurityS// "AdminSecurity.SelectedEntitiesText"
0xed86c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed871  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xed876  ldarg.0
0xed877  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::AddButton
0xed87c  ldarg.0
0xed87d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed882  ldstr    aMenuLabelAdd// "Menu_Label_Add"
0xed887  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed88c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0xed891  ldarg.0
0xed892  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::AddButton
0xed897  ldarg.0
0xed898  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed89d  ldstr    aAdminsecurityA_1// "AdminSecurity.AddButtonText"
0xed8a2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed8a7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0xed8ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0xed8b1  ldarg.0
0xed8b2  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::AddButton
0xed8b7  ldarg.0
0xed8b8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed8bd  ldstr    aAdminsecurityA_1// "AdminSecurity.AddButtonText"
0xed8c2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed8c7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0xed8cc  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0xed8d1  ldarg.0
0xed8d2  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::RemoveButton
0xed8d7  ldarg.0
0xed8d8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed8dd  ldstr    aButtonLabelRem// "Button_Label_Remove"
0xed8e2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed8e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0xed8ec  ldarg.0
0xed8ed  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::RemoveButton
0xed8f2  ldarg.0
0xed8f3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed8f8  ldstr    aAdminsecurityR// "AdminSecurity.RemoveButtonText"
0xed8fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed902  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0xed907  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0xed90c  ldarg.0
0xed90d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::RemoveButton
0xed912  ldarg.0
0xed913  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed918  ldstr    aAdminsecurityR// "AdminSecurity.RemoveButtonText"
0xed91d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed922  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0xed927  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0xed92c  ldarg.0
0xed92d  ldc.i4.1
0xed92e  call     instance void Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::EnableButtons(bool enable)
0xed933  ldarg.0
0xed934  call     instance void Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::PopulateEntityLists()
0xed939  ldarg.0
0xed93a  call     instance void Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::RenderEntityLists()
0xed93f  ldarg.0
0xed940  call     instance void Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::ConfigureRadioButton()
0xed945  ldarg.0
0xed946  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xed94b  ldstr    aLocidBlankMaxD// "LOCID_BLANK_MAX_DEPTH"
0xed950  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xed955  ldarg.0
0xed956  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed95b  ldstr    aHierarchysecur// "HierarchySecuritySettings.MaxDepthError"...
0xed960  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed965  ldc.i4.0
0xed966  newarr   [mscorlib]System.Object
0xed96b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xed970  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xed975  ldarg.0
0xed976  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xed97b  ldstr    aLocidFormsSave// "LOCID_FORMS_SAVE_CONFIRM_TITLE"
0xed980  ldarg.0
0xed981  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed986  ldstr    aWebFormsStyles_2// "Web._forms.styles.FORM.crm.htc_Title"
0xed98b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed990  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xed995  ldarg.0
0xed996  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xed99b  ldstr    aLocidMustSelec// "LOCID_MUST_SELECT_ENTITY_WARNING"
0xed9a0  ldarg.0
0xed9a1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xed9a6  ldstr    aSystemcustomiz_230// "SystemCustomization.QuickFindConfigurat"...
0xed9ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xed9b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xed9b5  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteHierarchicalSecurityConfiguration()
0xed9ba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xed9bf  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xed9c4  brtrue.s loc_EDA32
0xed9c6  ldarg.0
0xed9c7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::AddButton
0xed9cc  ldc.i4.1
0xed9cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xed9d2  ldarg.0
0xed9d3  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::RemoveButton
0xed9d8  ldc.i4.1
0xed9d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xed9de  ldarg.0
0xed9df  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::AvailableEntities
0xed9e4  ldc.i4.1
0xed9e5  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0xed9ea  ldarg.0
0xed9eb  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::SelectedEntities
0xed9f0  ldc.i4.1
0xed9f1  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0xed9f6  ldarg.0
0xed9f7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::ckEnableHSMConfiguration
0xed9fc  ldc.i4.1
0xed9fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xeda02  ldarg.0
0xeda03  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Radio Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::rdSelectHierarchyType
0xeda08  ldc.i4.1
0xeda09  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xeda0e  ldarg.0
0xeda0f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Number Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::txtHierarchyDepth
0xeda14  ldc.i4.1
0xeda15  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xeda1a  ldarg.0
0xeda1b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::AvailableEntitiesText
0xeda20  ldc.i4.1
0xeda21  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0xeda26  ldarg.0
0xeda27  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Pages.Tools.AdminSecurity.HierarchySecurityModelingSettings::SelectedEntitiesText
0xeda2c  ldc.i4.1
0xeda2d  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0xeda32  ret
```
