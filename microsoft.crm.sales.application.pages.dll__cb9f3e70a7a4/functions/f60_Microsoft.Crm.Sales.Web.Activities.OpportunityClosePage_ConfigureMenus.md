# Microsoft.Crm.Sales.Web.Activities.OpportunityClosePage::ConfigureMenus

- ea: `0xf60`
- end: `0xf83`
- name: `Microsoft.Crm.Sales.Web.Activities.OpportunityClosePage::ConfigureMenus`
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
0xf60  ldarg.0
0xf61  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0xf66  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar
0xf6b  dup
0xf6c  ldc.i4.2
0xf6d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::AddParameter(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.FormActionParameters)
0xf72  ldarg.0
0xf73  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0xf78  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0xf7d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck)
0xf82  ret
```
