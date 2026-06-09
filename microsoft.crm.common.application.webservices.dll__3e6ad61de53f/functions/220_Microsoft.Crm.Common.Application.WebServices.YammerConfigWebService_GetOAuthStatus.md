# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::GetOAuthStatus

- ea: `0x220`
- end: `0x281`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::GetOAuthStatus`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x220`

## string_xrefs

- `0x22a`: `YamTokenRefreshing`
- `0x24d`: `Completed`

## pseudocode

```c

```

## disassembly

```asm
0x220  call     class [System.Web]System.Web.HttpRequestBase [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Request()
0x225  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequestBase::get_Cookies()
0x22a  ldstr    aYamtokenrefres// "YamTokenRefreshing"
0x22f  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0x234  stloc.0
0x235  ldloc.0
0x236  brfalse.s loc_245
0x238  ldloc.0
0x239  callvirt instance string [System.Web]System.Web.HttpCookie::get_Value()
0x23e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x243  brfalse.s loc_247
0x245  ldnull
0x246  ret
0x247  ldloc.0
0x248  callvirt instance string [System.Web]System.Web.HttpCookie::get_Value()
0x24d  ldstr    aCompleted// "Completed"
0x252  ldc.i4.5
0x253  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x258  brtrue.s loc_25C
0x25a  ldnull
0x25b  ret
0x25c  call     class [System.Web]System.Web.HttpRequestBase [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Request()
0x261  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequestBase::get_Cookies()
0x266  ldstr    aYamoautherror// "YamOAuthError"
0x26b  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0x270  stloc.1
0x271  ldloc.1
0x272  brfalse.s loc_27B
0x274  ldloc.1
0x275  callvirt instance string [System.Web]System.Web.HttpCookie::get_Value()
0x27a  ret
0x27b  ldsfld   string [mscorlib]System.String::Empty
0x280  ret
```
