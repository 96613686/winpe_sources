# Microsoft.Crm.Marketing.Application.Pages.MA.FormActivityPage::ConfigureHeader

- ea: `0x3050`
- end: `0x3078`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.FormActivityPage::ConfigureHeader`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3130`

## string_xrefs

- `0x305c`: `LOCID_MC_TEMPLATE_MANDATORY`
- `0x3067`: `MC_Alert_TemplateIsMust`

## pseudocode

```c

```

## disassembly

```asm
0x3050  ldarg.0
0x3051  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignBasePage::ConfigureHeader()
0x3056  ldarg.0
0x3057  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x305c  ldstr    aLocidMcTemplat// "LOCID_MC_TEMPLATE_MANDATORY"
0x3061  ldarg.0
0x3062  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3067  ldstr    aMcAlertTemplat// "MC_Alert_TemplateIsMust"
0x306c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3071  ldc.i4.0
0x3072  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x3077  ret
```
