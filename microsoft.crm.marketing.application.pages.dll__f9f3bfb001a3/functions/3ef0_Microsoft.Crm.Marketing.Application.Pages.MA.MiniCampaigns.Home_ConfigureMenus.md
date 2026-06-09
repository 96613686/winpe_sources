# Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::ConfigureMenus

- ea: `0x3ef0`
- end: `0x3f07`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::ConfigureMenus`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x3ef0  ldarg.0
0x3ef1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0x3ef6  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar
0x3efb  ldarg.0
0x3efc  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaigns.Home::crmGrid
0x3f01  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar::Execute(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid)
0x3f06  ret
```
