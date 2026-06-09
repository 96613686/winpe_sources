# Microsoft.Crm.Sales.Web.Sfa.SalesOrderDetailPage::OnPreInit

- ea: `0x16d0`
- end: `0x172c`
- name: `Microsoft.Crm.Sales.Web.Sfa.SalesOrderDetailPage::OnPreInit`
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
0x16d0  ldarg.0
0x16d1  ldarg.1
0x16d2  call     instance void [System.Web]System.Web.UI.Page::OnPreInit(class [mscorlib]System.EventArgs)
0x16d7  ldarg.0
0x16d8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16dd  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x16e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x16e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x16ec  stloc.0
0x16ed  ldloc.0
0x16ee  ldstr    aUserdefinedEdi// "/userdefined/edit.aspx"
0x16f3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0x16f8  ldloc.0
0x16f9  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x16fe  ldstr    aEtc// "etc"
0x1703  ldc.i4   0x440
0x1708  stloc.1
0x1709  ldloca.s 1
0x170b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1710  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1715  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x171a  ldarg.0
0x171b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1720  ldloc.0
0x1721  callvirt instance string [mscorlib]System.Object::ToString()
0x1726  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0x172b  ret
```
