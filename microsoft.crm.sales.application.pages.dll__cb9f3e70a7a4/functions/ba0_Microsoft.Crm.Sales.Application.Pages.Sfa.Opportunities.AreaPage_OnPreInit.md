# Microsoft.Crm.Sales.Application.Pages.Sfa.Opportunities.AreaPage::OnPreInit

- ea: `0xba0`
- end: `0xbf7`
- name: `Microsoft.Crm.Sales.Application.Pages.Sfa.Opportunities.AreaPage::OnPreInit`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xba0  ldarg.0
0xba1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::OnPreInit()
0xba6  ldarg.0
0xba7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xbac  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0xbb1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbb6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbbb  stloc.0
0xbbc  ldloc.0
0xbbd  ldstr    aUserdefinedAre// "/userdefined/area.aspx"
0xbc2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0xbc7  ldloc.0
0xbc8  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xbcd  ldstr    aOtype// "oType"
0xbd2  ldc.i4.3
0xbd3  stloc.1
0xbd4  ldloca.s 1
0xbd6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbdb  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbe0  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xbe5  ldarg.0
0xbe6  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xbeb  ldloc.0
0xbec  callvirt instance string [mscorlib]System.Object::ToString()
0xbf1  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0xbf6  ret
```
