# Microsoft.Crm.Sales.Application.Pages.Sfa.Orders.AreaPage::OnPreInit

- ea: `0x9a0`
- end: `0x9fb`
- name: `Microsoft.Crm.Sales.Application.Pages.Sfa.Orders.AreaPage::OnPreInit`
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
0x9a0  ldarg.0
0x9a1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager::OnPreInit()
0x9a6  ldarg.0
0x9a7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9ac  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x9b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9bb  stloc.0
0x9bc  ldloc.0
0x9bd  ldstr    aUserdefinedAre// "/userdefined/area.aspx"
0x9c2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0x9c7  ldloc.0
0x9c8  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x9cd  ldstr    aOtype// "oType"
0x9d2  ldc.i4   0x440
0x9d7  stloc.1
0x9d8  ldloca.s 1
0x9da  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9df  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x9e4  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x9e9  ldarg.0
0x9ea  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x9ef  ldloc.0
0x9f0  callvirt instance string [mscorlib]System.Object::ToString()
0x9f5  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0x9fa  ret
```
