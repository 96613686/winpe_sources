# Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ReactivateCampaignResponse::ConfigureForm

- ea: `0xc10`
- end: `0xc46`
- name: `Microsoft.Crm.Marketing.Web.MA.CampaignResponse.Dialogs.ReactivateCampaignResponse::ConfigureForm`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xc10  ldarg.0
0xc11  ldarg.0
0xc12  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc17  ldstr    aWebMaCampaignr// "Web.MA.CampaignResponse.dlg_reactivatec"...
0xc1c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc21  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0xc26  ldarg.0
0xc27  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xc2c  ldc.i4.1
0xc2d  ldstr    aButtonLabelRea// "Button_Label_Reactivate"
0xc32  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons, string)
0xc37  pop
0xc38  ldarg.0
0xc39  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xc3e  ldc.i4.2
0xc3f  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0xc44  pop
0xc45  ret
```
