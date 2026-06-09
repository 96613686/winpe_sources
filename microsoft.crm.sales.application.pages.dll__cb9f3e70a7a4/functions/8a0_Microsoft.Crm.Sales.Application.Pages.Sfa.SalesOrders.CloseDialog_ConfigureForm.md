# Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::ConfigureForm

- ea: `0x8a0`
- end: `0x979`
- name: `Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::ConfigureForm`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8a0`

## pseudocode

```c

```

## disassembly

```asm
0x8a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8a5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8aa  ldc.i4   0x440
0x8af  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x8b4  stloc.0
0x8b5  ldarg.0
0x8b6  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::selStatus
0x8bb  ldloc.0
0x8bc  ldstr    aStatuscode// "statuscode"
0x8c1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x8c6  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x8cb  ldarg.0
0x8cc  ldfld    bool Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::IsOrderFulfillDialog
0x8d1  brfalse.s loc_912
0x8d3  ldarg.0
0x8d4  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::selStatus
0x8d9  ldc.i4.1
0x8da  newarr   [mscorlib]System.Int32
0x8df  dup
0x8e0  ldc.i4.0
0x8e1  ldstr    aSalesorder// "salesorder"
0x8e6  ldc.i4.3
0x8e7  stloc.1
0x8e8  ldloca.s 1
0x8ea  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.SalesOrderState
0x8f0  callvirt instance string [mscorlib]System.Object::ToString()
0x8f5  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x8fa  stelem.i4
0x8fb  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x900  ldarg.0
0x901  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::dateText
0x906  ldstr    aWebSfaSalesord_3// "Web.SFA.salesorders.aspx_51.dlg_close"
0x90b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x910  br.s     loc_94F
0x912  ldarg.0
0x913  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::selStatus
0x918  ldc.i4.1
0x919  newarr   [mscorlib]System.Int32
0x91e  dup
0x91f  ldc.i4.0
0x920  ldstr    aSalesorder// "salesorder"
0x925  ldc.i4.2
0x926  stloc.1
0x927  ldloca.s 1
0x929  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.SalesOrderState
0x92f  callvirt instance string [mscorlib]System.Object::ToString()
0x934  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x939  stelem.i4
0x93a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x93f  ldarg.0
0x940  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::dateText
0x945  ldstr    aWebSfaSalesord_4// "Web.SFA.salesorders.aspx_50.dlg_close"
0x94a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.Localization.Text::set_ResourceId(string)
0x94f  ldarg.0
0x950  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::closeDate
0x955  ldc.i4.0
0x956  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl::set_AllowBlankDate(bool)
0x95b  ldarg.0
0x95c  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.DateTimeControl Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::closeDate
0x961  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0x966  stloc.2
0x967  ldloca.s 2
0x969  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x96e  box      [mscorlib]System.DateTime
0x973  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x978  ret
```
