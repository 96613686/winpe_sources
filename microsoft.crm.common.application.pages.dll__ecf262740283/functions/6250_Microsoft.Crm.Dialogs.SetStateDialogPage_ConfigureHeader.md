# Microsoft.Crm.Dialogs.SetStateDialogPage::ConfigureHeader

- ea: `0x6250`
- end: `0x6267`
- name: `Microsoft.Crm.Dialogs.SetStateDialogPage::ConfigureHeader`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x625c`: `ActivitiesWebService`

## pseudocode

```c

```

## disassembly

```asm
0x6250  ldarg.0
0x6251  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigureHeader()
0x6256  ldarg.0
0x6257  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x625c  ldstr    aActivitieswebs// "ActivitiesWebService"
0x6261  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x6266  ret
```
