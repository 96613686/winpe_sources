# Microsoft.Crm.Sales.Web.Activities.QuoteClosePage::ConfigureMenus

- ea: `0xff0`
- end: `0x1013`
- name: `Microsoft.Crm.Sales.Web.Activities.QuoteClosePage::ConfigureMenus`
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
0xff0  ldarg.0
0xff1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmMenuBar
0xff6  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar
0xffb  dup
0xffc  ldc.i4.2
0xffd  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::AddParameter(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.FormActionParameters)
0x1002  ldarg.0
0x1003  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x1008  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0x100d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppFormMenuBar::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck)
0x1012  ret
```
