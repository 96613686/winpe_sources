# Microsoft.Crm.Common.Application.Pages.Dialogs.AppointmentDetailPage::Item_DataBoundReady

- ea: `0x197d0`
- end: `0x19897`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.AppointmentDetailPage::Item_DataBoundReady`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x19370`
- `0x19500`
- `0x19550`
- `0x197d0`

## string_xrefs

- `0x197e5`: `scheduledstart`
- `0x197fa`: `scheduledstart`
- `0x19816`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x197d0  ldarg.0
0x197d1  ldarg.1
0x197d2  ldarg.2
0x197d3  call     instance void Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::Item_DataBoundReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0x197d8  ldarg.0
0x197d9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::RetrieveCampaignActivity()
0x197de  stloc.0
0x197df  ldarg.2
0x197e0  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x197e5  ldstr    aScheduledstart// "scheduledstart"
0x197ea  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x197ef  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x197f4  stloc.1
0x197f5  ldloc.1
0x197f6  brfalse.s loc_19809
0x197f8  ldloc.1
0x197f9  ldloc.0
0x197fa  ldstr    aScheduledstart// "scheduledstart"
0x197ff  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19804  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x19809  ldarg.0
0x1980a  ldarg.2
0x1980b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetDueDateControl(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs eventArguments)
0x19810  stloc.2
0x19811  ldloc.2
0x19812  brfalse.s loc_19825
0x19814  ldloc.2
0x19815  ldloc.0
0x19816  ldstr    aScheduledend// "scheduledend"
0x1981b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19820  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x19825  ldarg.2
0x19826  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x1982b  ldstr    aDescription_0// "description"
0x19830  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x19835  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x1983a  stloc.3
0x1983b  ldloc.3
0x1983c  brfalse.s loc_19896
0x1983e  ldloc.0
0x1983f  ldstr    aRegardingobjec_0// "regardingobjectid"
0x19844  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19849  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x1984e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x19853  stloc.s  4
0x19855  ldstr    aCampaign_0// "campaign"
0x1985a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1985f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19864  newobj   instance void [Microsoft.Crm.Marketing.Application.Platform]Microsoft.Crm.Marketing.Application.Platform.Campaign::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x19869  stloc.s  5
0x1986b  ldloc.s  5
0x1986d  ldloc.s  4
0x1986f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x19874  ldstr    aColumnsetColum_2// "<columnset><column>objective</column></"...
0x19879  stloc.s  6
0x1987b  ldloc.s  5
0x1987d  ldloc.s  6
0x1987f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x19884  ldloc.3
0x19885  ldloc.s  5
0x19887  ldstr    aObjective// "objective"
0x1988c  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19891  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x19896  ret
```
