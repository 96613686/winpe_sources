# Microsoft.Crm.Common.Application.Controls.DownloadFailurePage::ConfigureHeader

- ea: `0x141c0`
- end: `0x141f8`
- name: `Microsoft.Crm.Common.Application.Controls.DownloadFailurePage::ConfigureHeader`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x141dc`: `/_common/styles/dialogs.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x141c0  ldarg.0
0x141c1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x141c6  ldarg.0
0x141c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x141cc  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0x141d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x141d6  ldarg.0
0x141d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x141dc  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x141e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x141e6  ldarg.0
0x141e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x141ec  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x141f1  ldnull
0x141f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x141f7  ret
```
