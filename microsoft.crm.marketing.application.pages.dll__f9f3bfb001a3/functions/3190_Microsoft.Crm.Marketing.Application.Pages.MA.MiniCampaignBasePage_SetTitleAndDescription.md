# Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::SetTitleAndDescription

- ea: `0x3190`
- end: `0x31bf`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::SetTitleAndDescription`
- size: `47`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2d00`
- `0x3010`
- `0x3080`
- `0x30f0`
- `0x3750`
- `0x37f0`

## pseudocode

```c

```

## disassembly

```asm
0x3190  ldarg.0
0x3191  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x3196  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm
0x319b  dup
0x319c  ldarg.0
0x319d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x31a2  ldarg.1
0x31a3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x31a8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::set_PageTitle(string)
0x31ad  ldarg.0
0x31ae  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x31b3  ldarg.2
0x31b4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x31b9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::set_PageDescription(string)
0x31be  ret
```
