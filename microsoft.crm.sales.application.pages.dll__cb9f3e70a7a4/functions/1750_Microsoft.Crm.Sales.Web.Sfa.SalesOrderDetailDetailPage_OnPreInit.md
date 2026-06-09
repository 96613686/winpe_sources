# Microsoft.Crm.Sales.Web.Sfa.SalesOrderDetailDetailPage::OnPreInit

- ea: `0x1750`
- end: `0x17ac`
- name: `Microsoft.Crm.Sales.Web.Sfa.SalesOrderDetailDetailPage::OnPreInit`
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
0x1750  ldarg.0
0x1751  ldarg.1
0x1752  call     instance void [System.Web]System.Web.UI.Page::OnPreInit(class [mscorlib]System.EventArgs)
0x1757  ldarg.0
0x1758  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x175d  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x1762  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1767  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x176c  stloc.0
0x176d  ldloc.0
0x176e  ldstr    aUserdefinedEdi// "/userdefined/edit.aspx"
0x1773  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0x1778  ldloc.0
0x1779  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x177e  ldstr    aEtc// "etc"
0x1783  ldc.i4   0x441
0x1788  stloc.1
0x1789  ldloca.s 1
0x178b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1790  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1795  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x179a  ldarg.0
0x179b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x17a0  ldloc.0
0x17a1  callvirt instance string [mscorlib]System.Object::ToString()
0x17a6  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0x17ab  ret
```
