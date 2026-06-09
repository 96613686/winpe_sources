# Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ConfigurePage

- ea: `0x3770`
- end: `0x37a7`
- name: `Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ConfigurePage`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x378c`: `/_grid/cmds/dlg_delete.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x3770  ldarg.0
0x3771  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x3776  ldarg.0
0x3777  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x377c  ldstr    aStaticGridCmds// "/_static/_grid/cmds/multiaction.js"
0x3781  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3786  ldarg.0
0x3787  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x378c  ldstr    aGridCmdsDlgDel// "/_grid/cmds/dlg_delete.aspx"
0x3791  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x3796  ldarg.0
0x3797  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x379c  ldstr    aGridCmdsDlgDea// "/_grid/cmds/dlg_deactivate.aspx"
0x37a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x37a6  ret
```
