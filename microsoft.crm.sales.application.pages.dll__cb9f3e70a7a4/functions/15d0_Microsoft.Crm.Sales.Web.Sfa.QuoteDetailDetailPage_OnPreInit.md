# Microsoft.Crm.Sales.Web.Sfa.QuoteDetailDetailPage::OnPreInit

- ea: `0x15d0`
- end: `0x162c`
- name: `Microsoft.Crm.Sales.Web.Sfa.QuoteDetailDetailPage::OnPreInit`
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
0x15d0  ldarg.0
0x15d1  ldarg.1
0x15d2  call     instance void [System.Web]System.Web.UI.Page::OnPreInit(class [mscorlib]System.EventArgs)
0x15d7  ldarg.0
0x15d8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x15dd  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x15e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x15e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15ec  stloc.0
0x15ed  ldloc.0
0x15ee  ldstr    aUserdefinedEdi// "/userdefined/edit.aspx"
0x15f3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0x15f8  ldloc.0
0x15f9  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x15fe  ldstr    aEtc// "etc"
0x1603  ldc.i4   0x43D
0x1608  stloc.1
0x1609  ldloca.s 1
0x160b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1610  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1615  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x161a  ldarg.0
0x161b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1620  ldloc.0
0x1621  callvirt instance string [mscorlib]System.Object::ToString()
0x1626  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0x162b  ret
```
