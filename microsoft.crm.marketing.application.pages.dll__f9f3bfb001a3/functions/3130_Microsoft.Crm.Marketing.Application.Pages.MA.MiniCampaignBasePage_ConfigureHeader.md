# Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::ConfigureHeader

- ea: `0x3130`
- end: `0x3189`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::ConfigureHeader`
- size: `89`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2c90`
- `0x2fe0`
- `0x3050`
- `0x30c0`
- `0x3770`
- `0x37a0`

## string_xrefs

- `0x315d`: `/_common/styles/dialogs.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x3130  ldarg.0
0x3131  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x3136  ldarg.0
0x3137  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x313c  ldstr    aLocidMcAlertCl// "LOCID_MC_ALERT_CLOSE"
0x3141  ldarg.0
0x3142  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3147  ldstr    aMcAlertClose// "MC_Alert_Close"
0x314c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3151  ldc.i4.0
0x3152  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3157  ldarg.0
0x3158  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x315d  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x3162  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x3167  ldarg.0
0x3168  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x316d  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x3172  ldnull
0x3173  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x3178  ldarg.0
0x3179  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x317e  ldstr    aMarketingautom// "MarketingAutomation"
0x3183  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x3188  ret
```
