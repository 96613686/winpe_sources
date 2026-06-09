# Microsoft.Crm.Service.Application.Pages.SM.ResourceGroups.Areas::ConfigurePage

- ea: `0x13200`
- end: `0x13247`
- name: `Microsoft.Crm.Service.Application.Pages.SM.ResourceGroups.Areas::ConfigurePage`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x1323c`: `/_grid/cmds/dlg_removeitems.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x13200  ldarg.0
0x13201  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAreaPage::ConfigurePage()
0x13206  ldarg.0
0x13207  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1320c  ldstr    aStaticControls_3// "/_static/_controls/lookup/lookup.js"
0x13211  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x13216  ldarg.0
0x13217  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1321c  ldstr    aStaticSmResour_1// "/_static/sm/resourcegroups/items.js"
0x13221  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x13226  ldarg.0
0x13227  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1322c  ldstr    aGridCmdsCmdAdd_0// "/_grid/cmds/cmd_additems.aspx"
0x13231  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x13236  ldarg.0
0x13237  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1323c  ldstr    aGridCmdsDlgRem// "/_grid/cmds/dlg_removeitems.aspx"
0x13241  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x13246  ret
```
