# Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetDueDateControl

- ea: `0x19550`
- end: `0x19566`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetDueDateControl`
- size: `22`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x19610`
- `0x197d0`
- `0x19950`
- `0x19aa0`
- `0x19c30`

## string_xrefs

- `0x19556`: `header_tab_scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x19550  ldarg.1
0x19551  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x19556  ldstr    aHeaderTabSched// "header_tab_scheduledend"
0x1955b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x19560  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x19565  ret
```
