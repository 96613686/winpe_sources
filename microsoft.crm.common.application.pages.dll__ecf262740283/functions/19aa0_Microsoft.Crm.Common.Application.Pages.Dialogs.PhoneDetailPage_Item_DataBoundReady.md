# Microsoft.Crm.Common.Application.Pages.Dialogs.PhoneDetailPage::Item_DataBoundReady

- ea: `0x19aa0`
- end: `0x19b3b`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.PhoneDetailPage::Item_DataBoundReady`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x19370`
- `0x19500`
- `0x19550`
- `0x19aa0`

## string_xrefs

- `0x19abc`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x19aa0  ldarg.0
0x19aa1  ldarg.1
0x19aa2  ldarg.2
0x19aa3  call     instance void Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::Item_DataBoundReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0x19aa8  ldarg.0
0x19aa9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::RetrieveCampaignActivity()
0x19aae  stloc.0
0x19aaf  ldarg.0
0x19ab0  ldarg.2
0x19ab1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetDueDateControl(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs eventArguments)
0x19ab6  stloc.1
0x19ab7  ldloc.1
0x19ab8  brfalse.s loc_19ACB
0x19aba  ldloc.1
0x19abb  ldloc.0
0x19abc  ldstr    aScheduledend// "scheduledend"
0x19ac1  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19ac6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x19acb  ldarg.2
0x19acc  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x19ad1  ldstr    aDescription_0// "description"
0x19ad6  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x19adb  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x19ae0  stloc.2
0x19ae1  ldloc.2
0x19ae2  brfalse.s loc_19B3A
0x19ae4  ldloc.0
0x19ae5  ldstr    aRegardingobjec_0// "regardingobjectid"
0x19aea  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19aef  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x19af4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x19af9  stloc.3
0x19afa  ldstr    aCampaign_0// "campaign"
0x19aff  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19b04  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19b09  newobj   instance void [Microsoft.Crm.Marketing.Application.Platform]Microsoft.Crm.Marketing.Application.Platform.Campaign::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x19b0e  stloc.s  4
0x19b10  ldloc.s  4
0x19b12  ldloc.3
0x19b13  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x19b18  ldstr    aColumnsetColum_2// "<columnset><column>objective</column></"...
0x19b1d  stloc.s  5
0x19b1f  ldloc.s  4
0x19b21  ldloc.s  5
0x19b23  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x19b28  ldloc.2
0x19b29  ldloc.s  4
0x19b2b  ldstr    aObjective// "objective"
0x19b30  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19b35  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x19b3a  ret
```
