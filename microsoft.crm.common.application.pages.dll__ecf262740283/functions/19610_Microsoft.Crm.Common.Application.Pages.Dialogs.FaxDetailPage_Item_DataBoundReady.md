# Microsoft.Crm.Common.Application.Pages.Dialogs.FaxDetailPage::Item_DataBoundReady

- ea: `0x19610`
- end: `0x196ab`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.FaxDetailPage::Item_DataBoundReady`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x19370`
- `0x19500`
- `0x19550`
- `0x19610`

## string_xrefs

- `0x1962c`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x19610  ldarg.0
0x19611  ldarg.1
0x19612  ldarg.2
0x19613  call     instance void Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::Item_DataBoundReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0x19618  ldarg.0
0x19619  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::RetrieveCampaignActivity()
0x1961e  stloc.0
0x1961f  ldarg.0
0x19620  ldarg.2
0x19621  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetDueDateControl(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs eventArguments)
0x19626  stloc.1
0x19627  ldloc.1
0x19628  brfalse.s loc_1963B
0x1962a  ldloc.1
0x1962b  ldloc.0
0x1962c  ldstr    aScheduledend// "scheduledend"
0x19631  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19636  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x1963b  ldarg.2
0x1963c  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x19641  ldstr    aDescription_0// "description"
0x19646  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1964b  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x19650  stloc.2
0x19651  ldloc.2
0x19652  brfalse.s loc_196AA
0x19654  ldloc.0
0x19655  ldstr    aRegardingobjec_0// "regardingobjectid"
0x1965a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1965f  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x19664  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x19669  stloc.3
0x1966a  ldstr    aCampaign_0// "campaign"
0x1966f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19674  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19679  newobj   instance void [Microsoft.Crm.Marketing.Application.Platform]Microsoft.Crm.Marketing.Application.Platform.Campaign::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1967e  stloc.s  4
0x19680  ldloc.s  4
0x19682  ldloc.3
0x19683  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x19688  ldstr    aColumnsetColum_2// "<columnset><column>objective</column></"...
0x1968d  stloc.s  5
0x1968f  ldloc.s  4
0x19691  ldloc.s  5
0x19693  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x19698  ldloc.2
0x19699  ldloc.s  4
0x1969b  ldstr    aObjective// "objective"
0x196a0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x196a5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x196aa  ret
```
