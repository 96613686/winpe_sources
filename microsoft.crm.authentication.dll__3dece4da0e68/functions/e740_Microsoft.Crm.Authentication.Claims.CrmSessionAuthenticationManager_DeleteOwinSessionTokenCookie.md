# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteOwinSessionTokenCookie

- ea: `0xe740`
- end: `0xe7ad`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteOwinSessionTokenCookie`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xe570`

## callees

- `0x2420`
- `0xe720`
- `0xe740`
- `0xe7b0`

## pseudocode

```c

```

## disassembly

```asm
0xe740  call     string Microsoft.Crm.Authentication.CrmPostAuthenticationCookieHelper::get_OwinCookieName()
0xe745  stloc.0
0xe746  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe74b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xe750  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequest::get_Cookies()
0xe755  ldloc.0
0xe756  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0xe75b  stloc.1
0xe75c  ldloc.1
0xe75d  brfalse.s loc_E76C
0xe75f  ldloc.1
0xe760  callvirt instance string [System.Web]System.Web.HttpCookie::get_Value()
0xe765  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xe76a  brfalse.s loc_E76D
0xe76c  ret
0xe76d  ldloc.0
0xe76e  stloc.2
0xe76f  ldc.i4.1
0xe770  stloc.3
0xe771  ldarg.0
0xe772  ldloc.2
0xe773  ldarg.1
0xe774  ldarg.2
0xe775  call     instance void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteSessionTokenCookie(string name, string path, string domain)
0xe77a  ldloc.0
0xe77b  ldloc.3
0xe77c  ldc.i4.1
0xe77d  add
0xe77e  dup
0xe77f  stloc.3
0xe780  call     string Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::GetOwinCookieChunkName(string baseName, int32 chunkIndex)
0xe785  stloc.2
0xe786  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe78b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xe790  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequest::get_Cookies()
0xe795  ldloc.2
0xe796  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0xe79b  stloc.1
0xe79c  ldloc.1
0xe79d  brfalse.s loc_E7AC
0xe79f  ldloc.1
0xe7a0  callvirt instance string [System.Web]System.Web.HttpCookie::get_Value()
0xe7a5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xe7aa  brfalse.s loc_E771
0xe7ac  ret
```
