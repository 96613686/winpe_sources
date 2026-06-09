# Microsoft.Crm.Service.Application.Pages.SM.ResourceGroups.DetailPage::ConfigurePage

- ea: `0x13470`
- end: `0x134a1`
- name: `Microsoft.Crm.Service.Application.Pages.SM.ResourceGroups.DetailPage::ConfigurePage`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x13496`: `/_grid/cmds/dlg_removeitems.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x13470  ldarg.0
0x13471  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13476  ldstr    aStaticSmResour_1// "/_static/sm/resourcegroups/items.js"
0x1347b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x13480  ldarg.0
0x13481  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13486  ldstr    aGridCmdsCmdAdd_0// "/_grid/cmds/cmd_additems.aspx"
0x1348b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x13490  ldarg.0
0x13491  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13496  ldstr    aGridCmdsDlgRem// "/_grid/cmds/dlg_removeitems.aspx"
0x1349b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x134a0  ret
```
