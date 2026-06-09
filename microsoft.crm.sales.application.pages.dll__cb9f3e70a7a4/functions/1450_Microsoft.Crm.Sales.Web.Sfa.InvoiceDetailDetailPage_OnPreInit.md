# Microsoft.Crm.Sales.Web.Sfa.InvoiceDetailDetailPage::OnPreInit

- ea: `0x1450`
- end: `0x14ac`
- name: `Microsoft.Crm.Sales.Web.Sfa.InvoiceDetailDetailPage::OnPreInit`
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
0x1450  ldarg.0
0x1451  ldarg.1
0x1452  call     instance void [System.Web]System.Web.UI.Page::OnPreInit(class [mscorlib]System.EventArgs)
0x1457  ldarg.0
0x1458  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x145d  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x1462  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1467  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x146c  stloc.0
0x146d  ldloc.0
0x146e  ldstr    aUserdefinedEdi// "/userdefined/edit.aspx"
0x1473  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0x1478  ldloc.0
0x1479  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x147e  ldstr    aEtc// "etc"
0x1483  ldc.i4   0x443
0x1488  stloc.1
0x1489  ldloca.s 1
0x148b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1490  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1495  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x149a  ldarg.0
0x149b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x14a0  ldloc.0
0x14a1  callvirt instance string [mscorlib]System.Object::ToString()
0x14a6  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0x14ab  ret
```
