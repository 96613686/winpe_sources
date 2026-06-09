# Microsoft.Crm.Common.Application.Pages.Dialogs.EmailDetailPage::Item_DataBoundReady

- ea: `0x19c30`
- end: `0x19d43`
- name: `Microsoft.Crm.Common.Application.Pages.Dialogs.EmailDetailPage::Item_DataBoundReady`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18dc0`
- `0x19370`
- `0x19500`
- `0x19550`
- `0x19c30`

## string_xrefs

- `0x19c7d`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x19c30  ldarg.0
0x19c31  ldarg.1
0x19c32  ldarg.2
0x19c33  call     instance void Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::Item_DataBoundReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0x19c38  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_SendAsUser()
0x19c3d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19c42  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19c47  brtrue.s loc_19C69
0x19c49  ldarg.2
0x19c4a  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x19c4f  ldstr    aFrom// "from"
0x19c54  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x19c59  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x19c5e  stloc.2
0x19c5f  ldloc.2
0x19c60  brfalse.s loc_19C69
0x19c62  ldloc.2
0x19c63  ldc.i4.1
0x19c64  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_ReadOnly(bool)
0x19c69  ldarg.0
0x19c6a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::RetrieveCampaignActivity()
0x19c6f  stloc.0
0x19c70  ldarg.0
0x19c71  ldarg.2
0x19c72  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::GetDueDateControl(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs eventArguments)
0x19c77  stloc.1
0x19c78  ldloc.1
0x19c79  brfalse.s loc_19C8C
0x19c7b  ldloc.1
0x19c7c  ldloc.0
0x19c7d  ldstr    aScheduledend// "scheduledend"
0x19c82  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19c87  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x19c8c  ldarg.2
0x19c8d  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x19c92  ldstr    aDescription_0// "description"
0x19c97  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x19c9c  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl
0x19ca1  dup
0x19ca2  ldc.i4.5
0x19ca3  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::set_Type(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.HtmlBarHeaderType)
0x19ca8  dup
0x19ca9  ldloc.0
0x19caa  ldstr    aRegardingobjec_0// "regardingobjectid"
0x19caf  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19cb4  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x19cb9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x19cbe  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x19cc3  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::set_EntityId(valuetype [mscorlib]System.Guid)
0x19cc8  ldstr    aCampaign_0// "campaign"
0x19ccd  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::set_EntityType(string)
0x19cd2  ldarg.2
0x19cd3  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x19cd8  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrudForm
0x19cdd  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormBody [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_FormBody()
0x19ce2  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x19ce7  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.ControlCollection::GetEnumerator()
0x19cec  stloc.3
0x19ced  br.s     loc_19D24
0x19cef  ldloc.3
0x19cf0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x19cf5  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormTab
0x19cfa  stloc.s  4
0x19cfc  ldloc.s  4
0x19cfe  brfalse.s loc_19D24
0x19d00  ldloc.s  4
0x19d02  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x19d07  ldarg.0
0x19d08  callvirt instance string Microsoft.Crm.Common.Application.Pages.Dialogs.ListBasicActivityPage::get_TabToHideId()
0x19d0d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19d12  brfalse.s loc_19D24
0x19d14  ldloc.s  4
0x19d16  ldc.i4.1
0x19d17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x19d1c  ldloc.s  4
0x19d1e  ldc.i4.0
0x19d1f  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x19d24  ldloc.3
0x19d25  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19d2a  brtrue.s loc_19CEF
0x19d2c  leave.s  loc_19D42
0x19d2e  ldloc.3
0x19d2f  isinst   [mscorlib]System.IDisposable
0x19d34  stloc.s  5
0x19d36  ldloc.s  5
0x19d38  brfalse.s loc_19D41
0x19d3a  ldloc.s  5
0x19d3c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19d41  endfinally
0x19d42  ret
```
