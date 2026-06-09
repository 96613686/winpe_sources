# Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::HandleXmlResponseType

- ea: `0x18c60`
- end: `0x18cf5`
- name: `Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::HandleXmlResponseType`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18170`
- `0x18960`

## callees

- `0x18c60`

## string_xrefs

- `0x18c99`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x18c60  ldarg.0
0x18c61  ldfld    string Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::responseType
0x18c66  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x18c6b  brtrue   loc_18CF3
0x18c70  ldarg.0
0x18c71  ldfld    string Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::responseType
0x18c76  ldstr    aXml// "xml"
0x18c7b  ldc.i4.5
0x18c7c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x18c81  brfalse.s loc_18CF3
0x18c83  ldarg.0
0x18c84  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0x18c89  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x18c8e  callvirt instance void [System.Web]System.Web.HttpResponse::ClearContent()
0x18c93  ldarg.0
0x18c94  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x18c99  ldstr    aTextXml// "text/xml"
0x18c9e  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x18ca3  ldarga.s 1
0x18ca5  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x18caa  brfalse.s loc_18CEA
0x18cac  ldarga.s 1
0x18cae  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x18cb3  ldc.i4.0
0x18cb4  newarr   [mscorlib]System.Object
0x18cb9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x18cbe  ldarg.0
0x18cbf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18cc4  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x18cc9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x18cce  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [System]System.Uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18cd3  stloc.0
0x18cd4  call     class [System.Xml]System.Xml.Serialization.XmlSerializer [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_XmlSerializer()
0x18cd9  ldarg.0
0x18cda  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x18cdf  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpResponse::get_OutputStream()
0x18ce4  ldloc.0
0x18ce5  callvirt instance void [System.Xml]System.Xml.Serialization.XmlSerializer::Serialize(class [mscorlib]System.IO.Stream, object)
0x18cea  ldarg.0
0x18ceb  ldc.i4.0
0x18cec  stfld    bool Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::writeDocType
0x18cf1  ldc.i4.1
0x18cf2  ret
0x18cf3  ldc.i4.0
0x18cf4  ret
```
