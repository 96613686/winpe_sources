# Microsoft.Crm.Sales.Web.Sfa.QuoteDetailPage::OnPreInit

- ea: `0x1650`
- end: `0x16ac`
- name: `Microsoft.Crm.Sales.Web.Sfa.QuoteDetailPage::OnPreInit`
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
0x1650  ldarg.0
0x1651  ldarg.1
0x1652  call     instance void [System.Web]System.Web.UI.Page::OnPreInit(class [mscorlib]System.EventArgs)
0x1657  ldarg.0
0x1658  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x165d  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x1662  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1667  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x166c  stloc.0
0x166d  ldloc.0
0x166e  ldstr    aUserdefinedEdi// "/userdefined/edit.aspx"
0x1673  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0x1678  ldloc.0
0x1679  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x167e  ldstr    aEtc// "etc"
0x1683  ldc.i4   0x43C
0x1688  stloc.1
0x1689  ldloca.s 1
0x168b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1690  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1695  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x169a  ldarg.0
0x169b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x16a0  ldloc.0
0x16a1  callvirt instance string [mscorlib]System.Object::ToString()
0x16a6  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0x16ab  ret
```
