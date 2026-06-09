# Microsoft.Crm.Web.Sfa.WorkflowTemplatePage::ConfigureHeader

- ea: `0x489b0`
- end: `0x48b8c`
- name: `Microsoft.Crm.Web.Sfa.WorkflowTemplatePage::ConfigureHeader`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x489ed`: `/_static/_common/styles/AutoToolTip.js`
- `0x489bc`: `/_common/styles/Dialogs.css.aspx`
- `0x48ab6`: `LOCID_NO_TEMPLATE_SELECTED`
- `0x48ac1`: `Web.SFA.Workflow.WorkflowTemplate.NoTemplateSelected`
- `0x489dd`: `/_static/_common/scripts/newdialog.js`
- `0x48a18`: `Web.SFA.Workflow.WorkflowTemplate.EmptyWorkflowName`
- `0x48ae2`: `Web.SFA.Workflow.WorkflowTemplate.PrimaryEntity`
- `0x48af8`: `LOCID_MORE_TEMPLATES_SELECTED`
- `0x48b03`: `Web.SFA.Workflow.WorkflowTemplate.MorethanoneTemplatesSelected`

## pseudocode

```c

```

## disassembly

```asm
0x489b0  ldarg.0
0x489b1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0x489b6  ldarg.0
0x489b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x489bc  ldstr    aCommonStylesDi_0// "/_common/styles/Dialogs.css.aspx"
0x489c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x489c6  ldarg.0
0x489c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x489cc  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x489d1  ldnull
0x489d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x489d7  ldarg.0
0x489d8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x489dd  ldstr    aStaticCommonSc_25// "/_static/_common/scripts/newdialog.js"
0x489e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x489e7  ldarg.0
0x489e8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x489ed  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x489f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x489f7  ldarg.0
0x489f8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x489fd  ldstr    aWorkflow_0// "Workflow"
0x48a02  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x48a07  ldarg.0
0x48a08  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x48a0d  ldstr    aLocidNameEmpty// "LOCID_NAME_EMPTY"
0x48a12  ldarg.0
0x48a13  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48a18  ldstr    aWebSfaWorkflow_81// "Web.SFA.Workflow.WorkflowTemplate.Empty"...
0x48a1d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x48a22  ldc.i4.0
0x48a23  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x48a28  ldarg.0
0x48a29  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x48a2e  ldstr    aLocidEntityEmp// "LOCID_ENTITY_EMPTY"
0x48a33  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x48a38  ldarg.0
0x48a39  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48a3e  ldstr    aA89f96f6A9f244// "A89F96F6-A9F2-44DC-A299-3B8D297DD46E"
0x48a43  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x48a48  ldc.i4.1
0x48a49  newarr   [mscorlib]System.Object
0x48a4e  dup
0x48a4f  ldc.i4.0
0x48a50  ldarg.0
0x48a51  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48a56  ldstr    aWebSfaWorkflow_82// "Web.SFA.Workflow.entity"
0x48a5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x48a60  stelem.ref
0x48a61  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x48a66  ldc.i4.0
0x48a67  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x48a6c  ldarg.0
0x48a6d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x48a72  ldstr    aLocidCategoryE// "LOCID_CATEGORY_EMPTY"
0x48a77  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x48a7c  ldarg.0
0x48a7d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48a82  ldstr    aA89f96f6A9f244// "A89F96F6-A9F2-44DC-A299-3B8D297DD46E"
0x48a87  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x48a8c  ldc.i4.1
0x48a8d  newarr   [mscorlib]System.Object
0x48a92  dup
0x48a93  ldc.i4.0
0x48a94  ldarg.0
0x48a95  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48a9a  ldstr    aWebSfaWorkflow_83// "Web.SFA.Workflow.Category"
0x48a9f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x48aa4  stelem.ref
0x48aa5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x48aaa  ldc.i4.0
0x48aab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x48ab0  ldarg.0
0x48ab1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x48ab6  ldstr    aLocidNoTemplat// "LOCID_NO_TEMPLATE_SELECTED"
0x48abb  ldarg.0
0x48abc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48ac1  ldstr    aWebSfaWorkflow_72// "Web.SFA.Workflow.WorkflowTemplate.NoTem"...
0x48ac6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x48acb  ldc.i4.0
0x48acc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x48ad1  ldarg.0
0x48ad2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x48ad7  ldstr    aLocidNoPrimary// "LOCID_NO_PRIMARYENTITY_SELECTED"
0x48adc  ldarg.0
0x48add  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48ae2  ldstr    aWebSfaWorkflow_84// "Web.SFA.Workflow.WorkflowTemplate.Prima"...
0x48ae7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x48aec  ldc.i4.0
0x48aed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x48af2  ldarg.0
0x48af3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x48af8  ldstr    aLocidMoreTempl// "LOCID_MORE_TEMPLATES_SELECTED"
0x48afd  ldarg.0
0x48afe  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48b03  ldstr    aWebSfaWorkflow_85// "Web.SFA.Workflow.WorkflowTemplate.Moret"...
0x48b08  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x48b0d  ldc.i4.0
0x48b0e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x48b13  ldarg.0
0x48b14  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x48b19  ldstr    aLocidGenericEn// "LOCID_GENERIC_ENTITY_DISPLAYNAME"
0x48b1e  ldarg.0
0x48b1f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48b24  ldstr    aWebSfaWorkflow_86// "Web.SFA.Workflow.GenericEntity"
0x48b29  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x48b2e  ldc.i4.0
0x48b2f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x48b34  ldarg.0
0x48b35  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x48b3a  ldstr    aLocidUniquenam// "LOCID_UNIQUENAME_ERRORMESSAGE"
0x48b3f  ldarg.0
0x48b40  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48b45  ldstr    aUniquenameErro// "UniqueName.ErrorMessage"
0x48b4a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x48b4f  ldc.i4.0
0x48b50  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x48b55  ldarg.0
0x48b56  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x48b5b  ldstr    aLocidSchemaNam// "LOCID_SCHEMA_NAME_EMPTY"
0x48b60  ldarg.0
0x48b61  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48b66  ldstr    aUniquenameEmpt// "UniqueName.Empty.ErrorMessage"
0x48b6b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x48b70  ldc.i4.0
0x48b71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x48b76  ldarg.0
0x48b77  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x48b7c  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x48b81  ldstr    aNameC// "name_c"
0x48b86  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x48b8b  ret
```
