# Microsoft.Crm.Service.Web.CS.ContractTemplateLookup::ConfigureHeader

- ea: `0x60c0`
- end: `0x6133`
- name: `Microsoft.Crm.Service.Web.CS.ContractTemplateLookup::ConfigureHeader`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x60cc`: `/_common/styles/dialogs.css.aspx`
- `0x60ed`: `/_static/_common/scripts/newdialog.js`
- `0x6108`: `Web.CS.contracts.lookup_template.aspx_102`
- `0x6123`: `Web.CS.contracts.lookup_template.aspx_28`

## pseudocode

```c

```

## disassembly

```asm
0x60c0  ldarg.0
0x60c1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0x60c6  ldarg.0
0x60c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x60cc  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x60d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x60d6  ldarg.0
0x60d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x60dc  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x60e1  ldnull
0x60e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x60e7  ldarg.0
0x60e8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x60ed  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/newdialog.js"
0x60f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x60f7  ldarg.0
0x60f8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x60fd  ldstr    aLocidNoItemsMe// "LOCID_NO_ITEMS_MESSAGE"
0x6102  ldarg.0
0x6103  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6108  ldstr    aWebCsContracts// "Web.CS.contracts.lookup_template.aspx_1"...
0x610d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6112  ldc.i4.0
0x6113  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x6118  ldarg.0
0x6119  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x611e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6123  ldstr    aWebCsContracts_0// "Web.CS.contracts.lookup_template.aspx_2"...
0x6128  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x612d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x6132  ret
```
