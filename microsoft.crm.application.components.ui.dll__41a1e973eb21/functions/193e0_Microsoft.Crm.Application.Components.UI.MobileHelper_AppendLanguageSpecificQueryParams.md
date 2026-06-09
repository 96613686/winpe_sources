# Microsoft.Crm.Application.Components.UI.MobileHelper::AppendLanguageSpecificQueryParams

- ea: `0x193e0`
- end: `0x1943d`
- name: `Microsoft.Crm.Application.Components.UI.MobileHelper::AppendLanguageSpecificQueryParams`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x19380`

## callees

- `0x193e0`
- `0x19440`

## string_xrefs

- `0x193e1`: `mobileUri`

## pseudocode

```c

```

## disassembly

```asm
0x193e0  ldarg.0
0x193e1  ldstr    aMobileuri// "mobileUri"
0x193e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x193eb  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x193f0  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x193f5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x193fa  stloc.0
0x193fb  ldloc.0
0x193fc  call     bool Microsoft.Crm.Application.Components.UI.MobileHelper::HasLanguageSpecificQueryParams(class [System]System.Collections.Specialized.NameValueCollection queryString)
0x19401  brfalse.s loc_1943B
0x19403  ldarg.0
0x19404  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x19409  ldstr    aClientType// "client_type"
0x1940e  ldloc.0
0x1940f  ldstr    aClientType// "client_type"
0x19414  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19419  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1941e  ldarg.0
0x1941f  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x19424  ldstr    aUserLcid// "user_lcid"
0x19429  ldloc.0
0x1942a  ldstr    aUserLcid// "user_lcid"
0x1942f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x19434  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x19439  ldc.i4.1
0x1943a  ret
0x1943b  ldc.i4.0
0x1943c  ret
```
