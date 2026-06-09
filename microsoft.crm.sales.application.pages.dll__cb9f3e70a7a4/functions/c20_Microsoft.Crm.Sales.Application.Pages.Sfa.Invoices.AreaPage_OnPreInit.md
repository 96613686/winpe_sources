# Microsoft.Crm.Sales.Application.Pages.Sfa.Invoices.AreaPage::OnPreInit

- ea: `0xc20`
- end: `0xc7b`
- name: `Microsoft.Crm.Sales.Application.Pages.Sfa.Invoices.AreaPage::OnPreInit`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xc20  ldarg.0
0xc21  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::OnPreInit()
0xc26  ldarg.0
0xc27  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc2c  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0xc31  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc36  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc3b  stloc.0
0xc3c  ldloc.0
0xc3d  ldstr    aUserdefinedAre// "/userdefined/area.aspx"
0xc42  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0xc47  ldloc.0
0xc48  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xc4d  ldstr    aOtype// "oType"
0xc52  ldc.i4   0x442
0xc57  stloc.1
0xc58  ldloca.s 1
0xc5a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc5f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc64  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xc69  ldarg.0
0xc6a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xc6f  ldloc.0
0xc70  callvirt instance string [mscorlib]System.Object::ToString()
0xc75  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0xc7a  ret
```
