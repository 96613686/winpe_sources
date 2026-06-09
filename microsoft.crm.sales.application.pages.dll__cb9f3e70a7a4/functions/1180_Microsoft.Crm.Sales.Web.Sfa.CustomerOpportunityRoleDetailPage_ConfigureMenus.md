# Microsoft.Crm.Sales.Web.Sfa.CustomerOpportunityRoleDetailPage::ConfigureMenus

- ea: `0x1180`
- end: `0x11a3`
- name: `Microsoft.Crm.Sales.Web.Sfa.CustomerOpportunityRoleDetailPage::ConfigureMenus`
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
0x1180  ldarg.0
0x1181  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0x1186  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar
0x118b  dup
0x118c  ldc.i4.2
0x118d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::AddParameter(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.FormActionParameters)
0x1192  ldarg.0
0x1193  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x1198  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0x119d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck)
0x11a2  ret
```
