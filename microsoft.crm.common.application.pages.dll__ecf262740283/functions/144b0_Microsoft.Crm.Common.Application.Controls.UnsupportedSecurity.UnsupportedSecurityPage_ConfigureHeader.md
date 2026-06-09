# Microsoft.Crm.Common.Application.Controls.UnsupportedSecurity.UnsupportedSecurityPage::ConfigureHeader

- ea: `0x144b0`
- end: `0x144d8`
- name: `Microsoft.Crm.Common.Application.Controls.UnsupportedSecurity.UnsupportedSecurityPage::ConfigureHeader`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x144bc`: `/_common/styles/dialogs.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x144b0  ldarg.0
0x144b1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x144b6  ldarg.0
0x144b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x144bc  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x144c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x144c6  ldarg.0
0x144c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x144cc  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x144d1  ldnull
0x144d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x144d7  ret
```
