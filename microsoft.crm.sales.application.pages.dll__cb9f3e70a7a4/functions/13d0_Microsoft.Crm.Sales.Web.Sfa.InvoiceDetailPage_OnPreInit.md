# Microsoft.Crm.Sales.Web.Sfa.InvoiceDetailPage::OnPreInit

- ea: `0x13d0`
- end: `0x142c`
- name: `Microsoft.Crm.Sales.Web.Sfa.InvoiceDetailPage::OnPreInit`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x13d0  ldarg.0
0x13d1  ldarg.1
0x13d2  call     instance void [System.Web]System.Web.UI.Page::OnPreInit(class [mscorlib]System.EventArgs)
0x13d7  ldarg.0
0x13d8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x13dd  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x13e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x13e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x13ec  stloc.0
0x13ed  ldloc.0
0x13ee  ldstr    aUserdefinedEdi// "/userdefined/edit.aspx"
0x13f3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0x13f8  ldloc.0
0x13f9  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x13fe  ldstr    aEtc// "etc"
0x1403  ldc.i4   0x442
0x1408  stloc.1
0x1409  ldloca.s 1
0x140b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1410  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1415  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x141a  ldarg.0
0x141b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1420  ldloc.0
0x1421  callvirt instance string [mscorlib]System.Object::ToString()
0x1426  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0x142b  ret
```
