# Microsoft.Crm.Sales.Web.Sfa.CustomerOpportunityRoleDetailPage::ConfigureForm

- ea: `0x1120`
- end: `0x1174`
- name: `Microsoft.Crm.Sales.Web.Sfa.CustomerOpportunityRoleDetailPage::ConfigureForm`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1120`

## pseudocode

```c

```

## disassembly

```asm
0x1120  ldarg.0
0x1121  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1126  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrudForm
0x112b  ldarg.0
0x112c  ldftn    instance void Microsoft.Crm.Sales.Web.Sfa.CustomerOpportunityRoleDetailPage::DataBound(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0x1132  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler::.ctor(object, native int)
0x1137  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::add_DataBound(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler)
0x113c  ldarg.0
0x113d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1142  ldarg.0
0x1143  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x1148  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x114d  ldarg.0
0x114e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x1153  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x1158  ldc.i4.2
0x1159  bne.un.s loc_1173
0x115b  ldarg.0
0x115c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1161  ldarg.0
0x1162  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x1167  ldc.i4.1
0x1168  ldnull
0x1169  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x116e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x1173  ret
```
