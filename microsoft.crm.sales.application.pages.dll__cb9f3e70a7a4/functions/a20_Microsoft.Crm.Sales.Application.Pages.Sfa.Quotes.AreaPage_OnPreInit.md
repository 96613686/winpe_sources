# Microsoft.Crm.Sales.Application.Pages.Sfa.Quotes.AreaPage::OnPreInit

- ea: `0xa20`
- end: `0xa7b`
- name: `Microsoft.Crm.Sales.Application.Pages.Sfa.Quotes.AreaPage::OnPreInit`
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
0xa20  ldarg.0
0xa21  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::OnPreInit()
0xa26  ldarg.0
0xa27  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xa2c  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0xa31  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa36  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa3b  stloc.0
0xa3c  ldloc.0
0xa3d  ldstr    aUserdefinedAre// "/userdefined/area.aspx"
0xa42  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0xa47  ldloc.0
0xa48  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xa4d  ldstr    aOtype// "oType"
0xa52  ldc.i4   0x43C
0xa57  stloc.1
0xa58  ldloca.s 1
0xa5a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa5f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa64  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa69  ldarg.0
0xa6a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xa6f  ldloc.0
0xa70  callvirt instance string [mscorlib]System.Object::ToString()
0xa75  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0xa7a  ret
```
