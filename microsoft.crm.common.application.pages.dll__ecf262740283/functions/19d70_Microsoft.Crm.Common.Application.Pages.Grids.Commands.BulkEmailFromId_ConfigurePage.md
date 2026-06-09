# Microsoft.Crm.Common.Application.Pages.Grids.Commands.BulkEmailFromId::ConfigurePage

- ea: `0x19d70`
- end: `0x19e52`
- name: `Microsoft.Crm.Common.Application.Pages.Grids.Commands.BulkEmailFromId::ConfigurePage`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x19d70`

## string_xrefs

- `0x19da7`: `template`
- `0x19e0e`: `template`
- `0x19dd8`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0x19d70  ldarg.0
0x19d71  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19d76  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x19d7b  ldstr    aFromid// "fromId"
0x19d80  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19d85  stloc.0
0x19d86  ldarg.0
0x19d87  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19d8c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x19d91  ldstr    aFromtype// "fromType"
0x19d96  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19d9b  stloc.1
0x19d9c  ldarg.0
0x19d9d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19da2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x19da7  ldstr    aTemplate// "template"
0x19dac  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19db1  stloc.2
0x19db2  ldarg.0
0x19db3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19db8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x19dbd  ldstr    aObjecttypecode// "objectTypeCode"
0x19dc2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19dc7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19dcc  call     int16 [mscorlib]System.Int16::Parse(string, class [mscorlib]System.IFormatProvider)
0x19dd1  stloc.3
0x19dd2  ldarg.0
0x19dd3  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x19dd8  ldstr    aTextXml// "text/xml"
0x19ddd  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x19de2  ldarg.0
0x19de3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x19de8  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x19ded  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x19df2  ldstr    aIds// "ids"
0x19df7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x19dfc  ldc.i4.1
0x19dfd  newarr   [mscorlib]System.Char
0x19e02  dup
0x19e03  ldc.i4.0
0x19e04  ldc.i4.s 0x2C
0x19e06  stelem.i2
0x19e07  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x19e0c  stloc.s  4
0x19e0e  ldstr    aTemplate// "template"
0x19e13  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19e18  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19e1d  newobj   instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Template::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x19e22  ldloc.2
0x19e23  ldloc.0
0x19e24  ldloc.1
0x19e25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19e2a  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x19e2f  ldloc.3
0x19e30  ldloc.s  4
0x19e32  ldloc.3
0x19e33  ldnull
0x19e34  callvirt instance void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Template::Send(string, string, int32, int32, string[], int32, string)
0x19e39  ldarg.0
0x19e3a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x19e3f  ldstr    aOk// "<ok/>"
0x19e44  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x19e49  leave.s  loc_19E51
0x19e4b  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x19e50  throw
0x19e51  ret
```
