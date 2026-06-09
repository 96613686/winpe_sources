# Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowStandardDialog

- ea: `0x6620`
- end: `0x6648`
- name: `Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowStandardDialog`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x64a0`
- `0x6560`
- `0x65f0`

## callees

- `0x6660`

## pseudocode

```c

```

## disassembly

```asm
0x6620  ldarg.0
0x6621  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6626  ldarg.1
0x6627  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x662c  ldarg.0
0x662d  ldarg.2
0x662e  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x6633  ldarg.0
0x6634  ldarg.3
0x6635  call     instance void Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::set_ErrorText(string value)
0x663a  ldarg.0
0x663b  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x6640  ldc.i4.1
0x6641  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x6646  pop
0x6647  ret
```
