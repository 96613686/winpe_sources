# Microsoft.Crm.Sales.Web.Sfa.CustomerOpportunityRoleDetailPage::DataBound

- ea: `0x11b0`
- end: `0x1206`
- name: `Microsoft.Crm.Sales.Web.Sfa.CustomerOpportunityRoleDetailPage::DataBound`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x11b0`

## pseudocode

```c

```

## disassembly

```asm
0x11b0  ldarg.2
0x11b1  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x11b6  ldstr    aCustomerid// "customerid"
0x11bb  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x11c0  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl
0x11c5  stloc.0
0x11c6  ldloc.0
0x11c7  callvirt instance object [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0x11cc  brfalse.s loc_1205
0x11ce  ldarg.2
0x11cf  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x11d4  ldstr    aOpportunityrol// "opportunityroleid"
0x11d9  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x11de  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelationshipRolePicklist
0x11e3  dup
0x11e4  ldloc.0
0x11e5  callvirt instance object [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Value()
0x11ea  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValueCollection
0x11ef  ldc.i4.0
0x11f0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValueCollection::get_Item(int32)
0x11f5  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x11fa  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelationshipRolePicklist::set_PrimaryObjectTypeCode(int32)
0x11ff  ldc.i4.3
0x1200  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.RelationshipRolePicklist::set_AssociatedObjectTypeCode(int32)
0x1205  ret
```
