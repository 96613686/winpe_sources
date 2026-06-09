# Microsoft.Crm.Service.Web.CreateCalendarDialogPage::ConfigurePage

- ea: `0x3ed0`
- end: `0x3ee7`
- name: `Microsoft.Crm.Service.Web.CreateCalendarDialogPage::ConfigurePage`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x3edc`: `/_common/styles/dialogs.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x3ed0  ldarg.0
0x3ed1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x3ed6  ldarg.0
0x3ed7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3edc  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x3ee1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x3ee6  ret
```
