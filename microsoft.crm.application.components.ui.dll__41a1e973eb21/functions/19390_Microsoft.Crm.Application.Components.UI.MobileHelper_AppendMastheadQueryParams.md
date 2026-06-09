# Microsoft.Crm.Application.Components.UI.MobileHelper::AppendMastheadQueryParams

- ea: `0x19390`
- end: `0x193e0`
- name: `Microsoft.Crm.Application.Components.UI.MobileHelper::AppendMastheadQueryParams`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x19380`

## callees

- `0x19390`

## string_xrefs

- `0x19391`: `mobileUri`

## pseudocode

```c

```

## disassembly

```asm
0x19390  ldarg.0
0x19391  ldstr    aMobileuri// "mobileUri"
0x19396  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1939b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x193a0  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x193a5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x193aa  stloc.0
0x193ab  ldc.i4.0
0x193ac  stloc.1
0x193ad  ldloc.0
0x193ae  ldstr    aHidemasthead// "HideMasthead"
0x193b3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x193b8  ldloca.s 1
0x193ba  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x193bf  brfalse.s loc_193DE
0x193c1  ldarg.0
0x193c2  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x193c7  ldstr    aHidemasthead// "HideMasthead"
0x193cc  ldloc.0
0x193cd  ldstr    aHidemasthead// "HideMasthead"
0x193d2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x193d7  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x193dc  ldc.i4.1
0x193dd  ret
0x193de  ldc.i4.0
0x193df  ret
```
