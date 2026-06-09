# Microsoft.Crm.Common.Application.Controls.UploadFailure.UploadFailurePage::ConfigureHeader

- ea: `0x14280`
- end: `0x142b8`
- name: `Microsoft.Crm.Common.Application.Controls.UploadFailure.UploadFailurePage::ConfigureHeader`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x1429c`: `/_common/styles/dialogs.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x14280  ldarg.0
0x14281  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0x14286  ldarg.0
0x14287  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1428c  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0x14291  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x14296  ldarg.0
0x14297  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1429c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x142a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x142a6  ldarg.0
0x142a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x142ac  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x142b1  ldnull
0x142b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x142b7  ret
```
