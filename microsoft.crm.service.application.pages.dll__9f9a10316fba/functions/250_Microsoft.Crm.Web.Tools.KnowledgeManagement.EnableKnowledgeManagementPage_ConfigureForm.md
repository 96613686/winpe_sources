# Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::ConfigureForm

- ea: `0x250`
- end: `0x3b5`
- name: `Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::ConfigureForm`
- size: `357`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x250`
- `0x3c0`
- `0x730`

## pseudocode

```c

```

## disassembly

```asm
0x250  ldarg.0
0x251  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x256  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm
0x25b  dup
0x25c  ldarg.0
0x25d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x262  ldstr    aWebToolsKnowle_10// "Web.Tools.KnowledgeManagement.SettingsP"...
0x267  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::set_PageTitle(string)
0x271  ldarg.0
0x272  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::btnReset
0x277  ldarg.0
0x278  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x27d  ldstr    aKmWizardButton// "KM_Wizard_Button_Tooltip_Reset"
0x282  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x287  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Title(string)
0x28c  ldarg.0
0x28d  call     instance void Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::PopulateParatureInstances()
0x292  ldc.i4.0
0x293  stloc.0
0x294  ldc.i4.0
0x295  stloc.1
0x296  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x29b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2a5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2aa  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x2af  stloc.2
0x2b0  ldloc.2
0x2b1  brfalse  loc_377
0x2b6  ldloc.2
0x2b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x2bc  brfalse  loc_377
0x2c1  ldloc.2
0x2c2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x2c7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_IsParature()
0x2cc  stloc.0
0x2cd  ldarg.0
0x2ce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2d3  ldstr    aLocidPatarurei// "LOCID_PATARUREINSTANCE_VALUE"
0x2d8  ldloc.2
0x2d9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x2de  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_ParatureInstance()
0x2e3  brfalse.s loc_2F2
0x2e5  ldloc.2
0x2e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x2eb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_ParatureInstance()
0x2f0  br.s     loc_2F7
0x2f2  ldstr    asc_15D82// ""
0x2f7  ldc.i4.0
0x2f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2fd  ldarg.0
0x2fe  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::txtSiteCollectionUrl
0x303  ldloc.2
0x304  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x309  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_ParatureUrl()
0x30e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::set_Text(string)
0x313  ldarg.0
0x314  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::txtAccountId
0x319  ldloc.2
0x31a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x31f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_AccountId()
0x324  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::set_Text(string)
0x329  ldarg.0
0x32a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::txtDepartment
0x32f  ldloc.2
0x330  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x335  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_DepartmentId()
0x33a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::set_Text(string)
0x33f  ldarg.0
0x340  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::txtSupportURL
0x345  ldloc.2
0x346  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x34b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_SupportURL()
0x350  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::set_Text(string)
0x355  ldarg.0
0x356  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::txtNativeCRMUrl
0x35b  ldloc.2
0x35c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x361  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_NativeCrmUrl()
0x366  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TextBox::set_Text(string)
0x36b  ldloc.2
0x36c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrentKMSettingsInfo()
0x371  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.KnowledgeManagement.KMSettings::get_UseExternalPortal()
0x376  stloc.1
0x377  ldarg.0
0x378  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x37d  ldstr    aLocidIsparatur// "LOCID_ISPARATURE_VALUE"
0x382  ldloc.0
0x383  brtrue.s loc_38C
0x385  ldstr    a0// "0"
0x38a  br.s     loc_391
0x38c  ldstr    a1// "1"
0x391  ldc.i4.0
0x392  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x397  ldarg.0
0x398  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::chkUseExtPortal
0x39d  ldloc.1
0x39e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox::set_Checked(bool)
0x3a3  ldarg.0
0x3a4  call     instance void Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::FillTable()
0x3a9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::get_BackButton()
0x3ae  ldc.i4.1
0x3af  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_Hidden(bool)
0x3b4  ret
```
