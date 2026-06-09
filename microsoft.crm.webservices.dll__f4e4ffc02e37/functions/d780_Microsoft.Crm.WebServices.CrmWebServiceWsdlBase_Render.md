# Microsoft.Crm.WebServices.CrmWebServiceWsdlBase::Render

- ea: `0xd780`
- end: `0xd7de`
- name: `Microsoft.Crm.WebServices.CrmWebServiceWsdlBase::Render`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xd630`
- `0xd6f0`
- `0xd770`

## string_xrefs

- `0xd7b3`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0xd780  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0xd785  stloc.0
0xd786  call     class Microsoft.Crm.WebServices.AspNetServiceDescriptionCache Microsoft.Crm.WebServices.AspNetServiceDescriptionCache::get_Instance()
0xd78b  ldarg.0
0xd78c  ldloc.0
0xd78d  callvirt instance string Microsoft.Crm.WebServices.CrmWebServiceWsdlBase::GetEndpoint(valuetype [mscorlib]System.Guid organizationId)
0xd792  ldarg.0
0xd793  ldfld    class [mscorlib]System.Type Microsoft.Crm.WebServices.CrmWebServiceWsdlBase::_webServiceType
0xd798  callvirt instance string [mscorlib]System.Type::get_FullName()
0xd79d  newobj   instance void Microsoft.Crm.WebServices.AspNetServiceDescriptionCacheKey::.ctor(string targetNamespace, string fullyQualifiedTypeName)
0xd7a2  ldloc.0
0xd7a3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xd7a8  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.WebServices.AspNetServiceDescriptionCacheKey, class [System.Web.Services]System.Web.Services.Description.ServiceDescription>::LookupEntry(void, var<u1>)
0xd7ad  ldarg.0
0xd7ae  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xd7b3  ldstr    aTextXml// "text/xml"
0xd7b8  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0xd7bd  ldarg.0
0xd7be  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xd7c3  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0xd7c8  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentEncoding(class [mscorlib]System.Text.Encoding)
0xd7cd  ldarg.0
0xd7ce  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xd7d3  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpResponse::get_OutputStream()
0xd7d8  callvirt instance void [System.Web.Services]System.Web.Services.Description.ServiceDescription::Write(class [mscorlib]System.IO.Stream)
0xd7dd  ret
```
