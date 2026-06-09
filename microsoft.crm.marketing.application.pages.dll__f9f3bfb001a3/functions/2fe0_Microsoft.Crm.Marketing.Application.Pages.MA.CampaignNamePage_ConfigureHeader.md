# Microsoft.Crm.Marketing.Application.Pages.MA.CampaignNamePage::ConfigureHeader

- ea: `0x2fe0`
- end: `0x3008`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.CampaignNamePage::ConfigureHeader`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3130`

## pseudocode

```c

```

## disassembly

```asm
0x2fe0  ldarg.0
0x2fe1  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::ConfigureHeader()
0x2fe6  ldarg.0
0x2fe7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2fec  ldstr    aLocidMcNameMan// "LOCID_MC_NAME_MANDATORY"
0x2ff1  ldarg.0
0x2ff2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2ff7  ldstr    aMcAlertNameism// "MC_Alert_NameIsMandatory"
0x2ffc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3001  ldc.i4.0
0x3002  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3007  ret
```
