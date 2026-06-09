# Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::OAuthHandleRequest

- ea: `0x8630`
- end: `0x8685`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::OAuthHandleRequest`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8a50`

## callees

- `0x8630`
- `0x8690`
- `0x8750`
- `0x87d0`

## pseudocode

```c

```

## disassembly

```asm
0x8630  ldarg.0
0x8631  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8636  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x863b  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::get_AllKeys()
0x8640  ldsfld   string[] Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::OAuthComletionParameters
0x8645  call     T0x2B000004
0x864a  call     T0x2B000005
0x864f  brtrue.s loc_8659
0x8651  ldarg.0
0x8652  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::RedirectToOAuthLoginPage()
0x8657  ldc.i4.1
0x8658  ret
0x8659  ldarg.0
0x865a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x865f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8664  ldstr    aCode// "code"
0x8669  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x866e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8673  brtrue.s loc_867D
0x8675  ldarg.0
0x8676  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::ReadOAuthToken()
0x867b  ldc.i4.0
0x867c  ret
0x867d  ldarg.0
0x867e  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::OAuthHandleError()
0x8683  ldc.i4.1
0x8684  ret
```
