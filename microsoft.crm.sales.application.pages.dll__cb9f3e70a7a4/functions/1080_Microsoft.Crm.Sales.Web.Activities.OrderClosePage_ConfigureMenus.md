# Microsoft.Crm.Sales.Web.Activities.OrderClosePage::ConfigureMenus

- ea: `0x1080`
- end: `0x10a3`
- name: `Microsoft.Crm.Sales.Web.Activities.OrderClosePage::ConfigureMenus`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1080  ldarg.0
0x1081  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0x1086  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar
0x108b  dup
0x108c  ldc.i4.2
0x108d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::AddParameter(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.FormActionParameters)
0x1092  ldarg.0
0x1093  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x1098  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0x109d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck)
0x10a2  ret
```
