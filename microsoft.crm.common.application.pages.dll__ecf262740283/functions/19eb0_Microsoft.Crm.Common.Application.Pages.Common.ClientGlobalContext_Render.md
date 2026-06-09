# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::Render

- ea: `0x19eb0`
- end: `0x19f04`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::Render`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x19eb0`
- `0x1a700`
- `0x1ab10`

## string_xrefs

- `0x19ec1`: `application/json`
- `0x19ed3`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x19eb0  ldstr    asc_1F1DE// ""
0x19eb5  stloc.0
0x19eb6  ldarg.0
0x19eb7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19ebc  callvirt instance string [System.Web]System.Web.HttpRequest::get_ContentType()
0x19ec1  ldstr    aApplicationJso// "application/json"
0x19ec6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19ecb  brfalse.s loc_19EE7
0x19ecd  ldarg.0
0x19ece  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x19ed3  ldstr    aApplicationJso// "application/json"
0x19ed8  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x19edd  ldarg.0
0x19ede  ldarg.1
0x19edf  ldc.i4.1
0x19ee0  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteOutGetGlobalContext(class [mscorlib]System.IO.TextWriter output, bool includeSensitiveInfo)
0x19ee5  br.s     loc_19EFC
0x19ee7  ldarg.0
0x19ee8  ldarg.1
0x19ee9  ldc.i4.0
0x19eea  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::WriteOutGetGlobalContext(class [mscorlib]System.IO.TextWriter output, bool includeSensitiveInfo)
0x19eef  ldloc.0
0x19ef0  ldarg.0
0x19ef1  call     instance string Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::GetJavascriptBlob()
0x19ef6  call     string [mscorlib]System.String::Concat(string, string)
0x19efb  stloc.0
0x19efc  ldarg.1
0x19efd  ldloc.0
0x19efe  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19f03  ret
```
