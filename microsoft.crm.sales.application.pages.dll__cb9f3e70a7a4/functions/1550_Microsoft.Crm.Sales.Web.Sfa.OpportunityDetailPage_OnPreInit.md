# Microsoft.Crm.Sales.Web.Sfa.OpportunityDetailPage::OnPreInit

- ea: `0x1550`
- end: `0x15a8`
- name: `Microsoft.Crm.Sales.Web.Sfa.OpportunityDetailPage::OnPreInit`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1550  ldarg.0
0x1551  ldarg.1
0x1552  call     instance void [System.Web]System.Web.UI.Page::OnPreInit(class [mscorlib]System.EventArgs)
0x1557  ldarg.0
0x1558  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x155d  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x1562  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1567  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x156c  stloc.0
0x156d  ldloc.0
0x156e  ldstr    aUserdefinedEdi// "/userdefined/edit.aspx"
0x1573  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0x1578  ldloc.0
0x1579  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x157e  ldstr    aEtc// "etc"
0x1583  ldc.i4.3
0x1584  stloc.1
0x1585  ldloca.s 1
0x1587  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x158c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1591  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1596  ldarg.0
0x1597  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x159c  ldloc.0
0x159d  callvirt instance string [mscorlib]System.Object::ToString()
0x15a2  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0x15a7  ret
```
