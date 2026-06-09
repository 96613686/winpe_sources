# Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::ConfigurePage

- ea: `0x10`
- end: `0x2c`
- name: `Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::ConfigurePage`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldarg.0
0x11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x16  ldstr    aStaticGridCmds// "/_static/_grid/cmds/multiaction.js"
0x1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x20  ldarg.0
0x21  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x26  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0x2b  ret
```
