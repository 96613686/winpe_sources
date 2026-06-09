# Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ConfigurePage

- ea: `0x3950`
- end: `0x3987`
- name: `Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ConfigurePage`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x396c`: `/_grid/cmds/dlg_delete.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x3950  ldarg.0
0x3951  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x3956  ldarg.0
0x3957  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x395c  ldstr    aStaticGridCmds// "/_static/_grid/cmds/multiaction.js"
0x3961  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3966  ldarg.0
0x3967  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x396c  ldstr    aGridCmdsDlgDel// "/_grid/cmds/dlg_delete.aspx"
0x3971  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x3976  ldarg.0
0x3977  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x397c  ldstr    aGridCmdsDlgDea// "/_grid/cmds/dlg_deactivate.aspx"
0x3981  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x3986  ret
```
