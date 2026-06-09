# Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::IsWabRequest

- ea: `0x7d90`
- end: `0x7e09`
- name: `Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::IsWabRequest`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x13f40`
- `0x15130`

## callees

- `0x7d90`
- `0x13ec0`

## pseudocode

```c

```

## disassembly

```asm
0x7d90  ldarg.0
0x7d91  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x7d96  callvirt instance string [System.Web]System.Web.HttpRequest::get_UserAgent()
0x7d9b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7da0  brtrue.s loc_7E07
0x7da2  ldarg.0
0x7da3  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x7da8  callvirt instance string [System.Web]System.Web.HttpRequest::get_UserAgent()
0x7dad  stloc.0
0x7dae  ldloc.0
0x7daf  ldstr    aIemobile110// "IEMobile/11.0"
0x7db4  ldc.i4.5
0x7db5  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x7dba  ldc.i4.m1
0x7dbb  ble.s    loc_7DF7
0x7dbd  ldsfld   string [mscorlib]System.String::Empty
0x7dc2  stloc.1
0x7dc3  ldarg.0
0x7dc4  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x7dc9  ldstr    aWctx// "wctx"
0x7dce  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x7dd3  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x7dd8  brtrue.s loc_7DF0
0x7dda  ldarg.0
0x7ddb  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x7de0  ldstr    aWctx// "wctx"
0x7de5  callvirt instance string [System.Web]System.Web.HttpRequest::get_Item(string)
0x7dea  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlDecode(string)
0x7def  stloc.1
0x7df0  ldloc.1
0x7df1  call     bool Microsoft.Crm.Authentication.Claims.HeaderAuthentication.KnownContextUrls::IsWindowsPhoneMocaWabUrl(string url)
0x7df6  ret
0x7df7  ldloc.0
0x7df8  ldstr    aMsauthhost// "MSAuthHost"
0x7dfd  ldc.i4.5
0x7dfe  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x7e03  ldc.i4.m1
0x7e04  cgt
0x7e06  ret
0x7e07  ldc.i4.0
0x7e08  ret
```
