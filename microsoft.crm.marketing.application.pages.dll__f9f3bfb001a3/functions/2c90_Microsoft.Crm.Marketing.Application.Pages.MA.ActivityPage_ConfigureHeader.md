# Microsoft.Crm.Marketing.Application.Pages.MA.ActivityPage::ConfigureHeader

- ea: `0x2c90`
- end: `0x2cfa`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.ActivityPage::ConfigureHeader`
- size: `106`
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
0x2c90  ldarg.0
0x2c91  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::ConfigureHeader()
0x2c96  ldarg.0
0x2c97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2c9c  ldstr    aLocidMcTypeMan// "LOCID_MC_TYPE_MANDATORY"
0x2ca1  ldarg.0
0x2ca2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2ca7  ldstr    aMcAlertChoosea// "MC_Alert_ChooseActivityType"
0x2cac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2cb1  ldc.i4.0
0x2cb2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2cb7  ldarg.0
0x2cb8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2cbd  ldstr    aLocidMcOwnerMa// "LOCID_MC_OWNER_MANDATORY"
0x2cc2  ldarg.0
0x2cc3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2cc8  ldstr    aMcAlertChooseo// "MC_Alert_ChooseOwnerOption"
0x2ccd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2cd2  ldc.i4.0
0x2cd3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2cd8  ldarg.0
0x2cd9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2cde  ldstr    aLocidMcQueueMa// "LOCID_MC_QUEUE_MANDATORY"
0x2ce3  ldarg.0
0x2ce4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2ce9  ldstr    aMcAlertChooseq// "MC_Alert_ChooseQueue"
0x2cee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2cf3  ldc.i4.0
0x2cf4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2cf9  ret
```
