# Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeCampaignPage::ConfigureHeader

- ea: `0x30c0`
- end: `0x30e8`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MailMergeCampaignPage::ConfigureHeader`
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
0x30c0  ldarg.0
0x30c1  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::ConfigureHeader()
0x30c6  ldarg.0
0x30c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x30cc  ldstr    aLocidMcBtnLaun// "LOCID_MC_BTN_LAUNCHWORD"
0x30d1  ldarg.0
0x30d2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x30d7  ldstr    aMcButtonLaunch// "MC_Button_LaunchWord"
0x30dc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x30e1  ldc.i4.0
0x30e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x30e7  ret
```
