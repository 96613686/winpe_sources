# Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::ConfigureHeader

- ea: `0x19400`
- end: `0x1944a`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::ConfigureHeader`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x19780`

## callees

- `0x193f0`
- `0x19400`

## string_xrefs

- `0x1940c`: `LOCID_MC_TEMPLATE_MANDATORY`
- `0x19417`: `MC_Alert_TemplateIsMust`

## pseudocode

```c

```

## disassembly

```asm
0x19400  ldarg.0
0x19401  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigureHeader()
0x19406  ldarg.0
0x19407  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1940c  ldstr    aLocidMcTemplat// "LOCID_MC_TEMPLATE_MANDATORY"
0x19411  ldarg.0
0x19412  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x19417  ldstr    aMcAlertTemplat// "MC_Alert_TemplateIsMust"
0x1941c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19421  ldc.i4.0
0x19422  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x19427  ldarg.0
0x19428  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::get_CurrentActivity()
0x1942d  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Disabled()
0x19432  brtrue.s loc_19449
0x19434  ldarg.0
0x19435  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1943a  ldstr    aSetfocus// "SetFocus"
0x1943f  ldstr    aGetSubjectFocu// "$get('subject').focus();"
0x19444  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x19449  ret
```
