# Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ConfigurePage

- ea: `0x3af0`
- end: `0x3b17`
- name: `Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ConfigurePage`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x3b0c`: `/_grid/cmds/dlg_delete.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x3af0  ldarg.0
0x3af1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x3af6  ldarg.0
0x3af7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3afc  ldstr    aStaticGridCmds// "/_static/_grid/cmds/multiaction.js"
0x3b01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3b06  ldarg.0
0x3b07  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x3b0c  ldstr    aGridCmdsDlgDel// "/_grid/cmds/dlg_delete.aspx"
0x3b11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x3b16  ret
```
