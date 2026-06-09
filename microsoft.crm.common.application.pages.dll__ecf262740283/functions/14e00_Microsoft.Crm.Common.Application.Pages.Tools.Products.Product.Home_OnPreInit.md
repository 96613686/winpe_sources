# Microsoft.Crm.Common.Application.Pages.Tools.Products.Product.Home::OnPreInit

- ea: `0x14e00`
- end: `0x14e6c`
- name: `Microsoft.Crm.Common.Application.Pages.Tools.Products.Product.Home::OnPreInit`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x14e4f`: `DisableCreate`

## pseudocode

```c

```

## disassembly

```asm
0x14e00  ldarg.0
0x14e01  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHomepageBase::OnPreInit()
0x14e06  ldarg.0
0x14e07  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14e0c  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x14e11  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x14e16  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14e1b  stloc.0
0x14e1c  ldloc.0
0x14e1d  ldstr    aRootHomepageAs// "/_root/homepage.aspx"
0x14e22  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0x14e27  ldloc.0
0x14e28  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x14e2d  ldstr    aEtc// "etc"
0x14e32  ldc.i4   0x400
0x14e37  stloc.1
0x14e38  ldloca.s 1
0x14e3a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14e3f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x14e44  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x14e49  ldloc.0
0x14e4a  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x14e4f  ldstr    aDisablecreate// "DisableCreate"
0x14e54  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::Remove(var<u1>)
0x14e59  pop
0x14e5a  ldarg.0
0x14e5b  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x14e60  ldloc.0
0x14e61  callvirt instance string [mscorlib]System.Object::ToString()
0x14e66  callvirt instance void [System.Web]System.Web.HttpResponse::Redirect(string)
0x14e6b  ret
```
