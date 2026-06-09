# Microsoft.Crm.Service.Dialogs.DefaultSlaApplicationDialogPage::OnPostBack

- ea: `0x2760`
- end: `0x27fa`
- name: `Microsoft.Crm.Service.Dialogs.DefaultSlaApplicationDialogPage::OnPostBack`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x26f0`

## callees

- `0x2760`
- `0x2800`

## string_xrefs

- `0x2766`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x2760  ldarg.0
0x2761  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x2766  ldstr    aTextXml// "text/xml"
0x276b  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x2770  ldarg.0
0x2771  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2776  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x277b  ldstr    aIid// "iId"
0x2780  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2785  stloc.0
0x2786  ldstr    aSla// "sla"
0x278b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2790  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2795  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x279a  dup
0x279b  ldloc.0
0x279c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x27a1  dup
0x27a2  ldstr    aIsdefault// "isdefault"
0x27a7  ldc.i4.1
0x27a8  box      [mscorlib]System.Boolean
0x27ad  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x27b2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27b7  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27bc  leave.s  loc_27F3
0x27be  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x27c3  throw
0x27c4  stloc.1
0x27c5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x27ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x27cf  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x27d4  ldstr    a0_0// "{0}"
0x27d9  ldc.i4.1
0x27da  newarr   [mscorlib]System.Object
0x27df  dup
0x27e0  ldc.i4.0
0x27e1  ldstr    aErrorEncounter_0// "Error encountered in post back of Merge"...
0x27e6  stelem.ref
0x27e7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x27ec  ldloc.1
0x27ed  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x27f2  throw
0x27f3  ldarg.0
0x27f4  call     instance void Microsoft.Crm.Service.Dialogs.DefaultSlaApplicationDialogPage::SendOK()
0x27f9  ret
```
