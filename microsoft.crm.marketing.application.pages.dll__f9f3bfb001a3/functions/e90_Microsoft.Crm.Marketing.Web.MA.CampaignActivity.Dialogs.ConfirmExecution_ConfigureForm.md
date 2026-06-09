# Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmExecution::ConfigureForm

- ea: `0xe90`
- end: `0xec9`
- name: `Microsoft.Crm.Marketing.Web.MA.CampaignActivity.Dialogs.ConfirmExecution::ConfigureForm`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xe90  ldarg.0
0xe91  ldarg.0
0xe92  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe97  ldstr    aConfirmExecuti// "Confirm_Execution_Dlg_Title"
0xe9c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xea1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0xea6  ldarg.0
0xea7  ldarg.0
0xea8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xead  ldstr    aConfirmExecuti_0// "Confirm_Execution_Dlg_Desc"
0xeb2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeb7  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0xebc  ldarg.0
0xebd  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xec2  ldc.i4.3
0xec3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButtons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0xec8  ret
```
