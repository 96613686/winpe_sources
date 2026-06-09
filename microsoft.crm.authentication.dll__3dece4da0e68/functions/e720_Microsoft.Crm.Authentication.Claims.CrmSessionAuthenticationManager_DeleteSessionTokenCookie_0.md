# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteSessionTokenCookie_0

- ea: `0xe720`
- end: `0xe734`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteSessionTokenCookie_0`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xe410`
- `0xe570`
- `0xe740`

## pseudocode

```c

```

## disassembly

```asm
0xe720  ldarg.0
0xe721  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe726  ldarg.1
0xe727  ldarg.2
0xe728  ldarg.3
0xe729  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe72e  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::Delete(string, string, string, class [System.Web]System.Web.HttpContext)
0xe733  ret
```
