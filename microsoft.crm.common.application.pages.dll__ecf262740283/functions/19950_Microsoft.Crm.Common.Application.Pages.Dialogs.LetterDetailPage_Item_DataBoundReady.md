# Microsoft.Crm.Common.Application.Pages.Dialogs.LetterDetailPage::Item_DataBoundReady

- ea: `0x19950`
- end: `0x199eb`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.LetterDetailPage::Item_DataBoundReady`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x19370`
- `0x19500`
- `0x19550`
- `0x19950`

## string_xrefs

- `0x1996c`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x19950  ldarg.0
0x19951  ldarg.1
0x19952  ldarg.2
0x19953  call     instance void Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::Item_DataBoundReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0x19958  ldarg.0
0x19959  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::RetrieveCampaignActivity()
0x1995e  stloc.0
0x1995f  ldarg.0
0x19960  ldarg.2
0x19961  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetDueDateControl(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs eventArguments)
0x19966  stloc.1
0x19967  ldloc.1
0x19968  brfalse.s loc_1997B
0x1996a  ldloc.1
0x1996b  ldloc.0
0x1996c  ldstr    aScheduledend// "scheduledend"
0x19971  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19976  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x1997b  ldarg.2
0x1997c  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x19981  ldstr    aDescription_0// "description"
0x19986  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1998b  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x19990  stloc.2
0x19991  ldloc.2
0x19992  brfalse.s loc_199EA
0x19994  ldloc.0
0x19995  ldstr    aRegardingobjec_0// "regardingobjectid"
0x1999a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1999f  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x199a4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x199a9  stloc.3
0x199aa  ldstr    aCampaign_0// "campaign"
0x199af  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x199b4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x199b9  newobj   instance void [Microsoft.Crm.Marketing.Application.Platform]Microsoft.Crm.Marketing.Application.Platform.Campaign::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x199be  stloc.s  4
0x199c0  ldloc.s  4
0x199c2  ldloc.3
0x199c3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x199c8  ldstr    aColumnsetColum_2// "<columnset><column>objective</column></"...
0x199cd  stloc.s  5
0x199cf  ldloc.s  4
0x199d1  ldloc.s  5
0x199d3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x199d8  ldloc.2
0x199d9  ldloc.s  4
0x199db  ldstr    aObjective// "objective"
0x199e0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x199e5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x199ea  ret
```
