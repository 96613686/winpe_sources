# Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderEmailFollowup

- ea: `0xf9c0`
- end: `0xfa07`
- name: `Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderEmailFollowup`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf970`

## callees

- `0xfa70`

## string_xrefs

- `0xf9ed`: `<columnset><column>subject</column><column>description</column><column>compressed</column><column>actualend</column><column>from</column><column>to</column><column>cc</column></columnset>`

## pseudocode

```c

```

## disassembly

```asm
0xf9c0  ldc.i4.0
0xf9c1  stloc.0
0xf9c2  ldstr    aEmail// "email"
0xf9c7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf9cc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf9d1  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Email::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0xf9d6  dup
0xf9d7  ldarg.0
0xf9d8  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::_entityId
0xf9dd  ldstr    aB// "B"
0xf9e2  call     instance string [mscorlib]System.Guid::ToString(string)
0xf9e7  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0xf9ec  dup
0xf9ed  ldstr    aColumnsetColum_0// "<columnset><column>subject</column><col"...
0xf9f2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0xf9f7  callvirt instance string [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Email::BuildEmailFollowUpBody()
0xf9fc  stloc.1
0xf9fd  ldarg.0
0xf9fe  ldarg.1
0xf9ff  ldloc.1
0xfa00  ldloc.0
0xfa01  call     instance void Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderHtml(class [System.Web]System.Web.UI.HtmlTextWriter writer, string rawData, bool unblockContent)
0xfa06  ret
```
