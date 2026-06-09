# Microsoft.Crm.Sales.Web.Sfa.OpportunityProductDetailPage::OnPreInit

- ea: `0x14d0`
- end: `0x152c`
- name: `Microsoft.Crm.Sales.Web.Sfa.OpportunityProductDetailPage::OnPreInit`
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
0x14d0  ldarg.0
0x14d1  ldarg.1
0x14d2  call     instance void [System.Web]System.Web.UI.Page::OnPreInit(class [mscorlib]System.EventArgs)
0x14d7  ldarg.0
0x14d8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14dd  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x14e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14ec  stloc.0
0x14ed  ldloc.0
0x14ee  ldstr    aUserdefinedEdi// "/userdefined/edit.aspx"
0x14f3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0x14f8  ldloc.0
0x14f9  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x14fe  ldstr    aEtc// "etc"
0x1503  ldc.i4   0x43B
0x1508  stloc.1
0x1509  ldloca.s 1
0x150b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1510  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1515  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x151a  ldarg.0
0x151b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1520  ldloc.0
0x1521  callvirt instance string [mscorlib]System.Object::ToString()
0x1526  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0x152b  ret
```
