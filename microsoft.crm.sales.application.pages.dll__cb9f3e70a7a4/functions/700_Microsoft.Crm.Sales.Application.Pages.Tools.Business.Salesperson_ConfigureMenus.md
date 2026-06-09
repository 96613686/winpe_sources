# Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::ConfigureMenus

- ea: `0x700`
- end: `0x729`
- name: `Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::ConfigureMenus`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x700  ldarg.0
0x701  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0x706  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar
0x70b  dup
0x70c  ldarg.0
0x70d  ldftn    instance void Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::MenuReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs e)
0x713  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler::.ctor(object, native int)
0x718  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::set_OnMenuReady(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuReadyEventHandler)
0x71d  ldarg.0
0x71e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Sales.Application.Pages.Tools.Business.Salesperson::crmGrid
0x723  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar::Execute(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid)
0x728  ret
```
