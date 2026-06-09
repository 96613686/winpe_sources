# Microsoft.Crm.Sales.Application.Pages.Sfa.Quotes.GetQuantityDecimalXmlAcceptor::ConfigurePage

- ea: `0xaa0`
- end: `0xb75`
- name: `Microsoft.Crm.Sales.Application.Pages.Sfa.Quotes.GetQuantityDecimalXmlAcceptor::ConfigurePage`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xaa0`

## string_xrefs

- `0xaa6`: `text/xml`

## pseudocode

```c

```

## disassembly

```asm
0xaa0  ldarg.0
0xaa1  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xaa6  ldstr    aTextXml// "text/xml"
0xaab  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0xab0  ldloca.s 0
0xab2  ldarg.0
0xab3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xab8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xabd  ldstr    aObjectid// "objectId"
0xac2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xac7  call     instance void [mscorlib]System.Guid::.ctor(string)
0xacc  ldloca.s 1
0xace  ldarg.0
0xacf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xad4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xad9  ldstr    aProductid// "productId"
0xade  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xae3  call     instance void [mscorlib]System.Guid::.ctor(string)
0xae8  ldloca.s 2
0xaea  ldarg.0
0xaeb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xaf0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xaf5  ldstr    aUomid// "uomId"
0xafa  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xaff  call     instance void [mscorlib]System.Guid::.ctor(string)
0xb04  ldarg.0
0xb05  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb0a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xb0f  ldstr    aObjecttypecode// "objectTypeCode"
0xb14  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb19  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb1e  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0xb23  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb28  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb2d  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xb32  ldloc.0
0xb33  ldloc.1
0xb34  ldloc.2
0xb35  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb3a  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::GetQuantityDecimal(string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb3f  stloc.3
0xb40  ldloc.3
0xb41  ldc.i4.0
0xb42  bge.s    loc_B46
0xb44  ldc.i4.5
0xb45  stloc.3
0xb46  ldarg.0
0xb47  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xb4c  ldstr    aQuantitydecima// "<quantitydecimal>"
0xb51  ldloca.s 3
0xb53  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb58  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xb5d  ldstr    aQuantitydecima_0// "</quantitydecimal>"
0xb62  call     string [mscorlib]System.String::Concat(string, string, string)
0xb67  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0xb6c  leave.s  loc_B74
0xb6e  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0xb73  throw
0xb74  ret
```
