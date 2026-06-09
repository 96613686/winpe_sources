# Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::RemoveAuthCookies

- ea: `0xd5d0`
- end: `0xd657`
- name: `Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::RemoveAuthCookies`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xd660`
- `0xd9f0`

## callees

- `0xd5b0`
- `0xd5d0`
- `0xe660`

## pseudocode

```c

```

## disassembly

```asm
0xd5d0  call     class [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule [System.IdentityModel.Services]System.IdentityModel.Services.FederatedAuthentication::get_SessionAuthenticationModule()
0xd5d5  callvirt instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xd5da  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_Name()
0xd5df  stloc.0
0xd5e0  ldc.i4.0
0xd5e1  stloc.1
0xd5e2  ldarg.0
0xd5e3  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xd5e8  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequest::get_Cookies()
0xd5ed  ldloc.0
0xd5ee  ldloc.1
0xd5ef  call     string Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::GetChunkName(string baseName, int32 chunkIndex)
0xd5f4  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0xd5f9  stloc.2
0xd5fa  br.s     loc_D62E
0xd5fc  ldarg.0
0xd5fd  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xd602  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequest::get_Cookies()
0xd607  ldloc.2
0xd608  callvirt instance string [System.Web]System.Web.HttpCookie::get_Name()
0xd60d  callvirt instance void [System.Web]System.Web.HttpCookieCollection::Remove(string)
0xd612  ldarg.0
0xd613  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xd618  callvirt instance class [System.Web]System.Web.HttpCookieCollection [System.Web]System.Web.HttpRequest::get_Cookies()
0xd61d  ldloc.0
0xd61e  ldloc.1
0xd61f  ldc.i4.1
0xd620  add
0xd621  dup
0xd622  stloc.1
0xd623  call     string Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::GetChunkName(string baseName, int32 chunkIndex)
0xd628  callvirt instance class [System.Web]System.Web.HttpCookie [System.Web]System.Web.HttpCookieCollection::get_Item(string)
0xd62d  stloc.2
0xd62e  ldloc.2
0xd62f  brtrue.s loc_D5FC
0xd631  call     class [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule [System.IdentityModel.Services]System.IdentityModel.Services.FederatedAuthentication::get_SessionAuthenticationModule()
0xd636  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_ContextSessionSecurityToken()
0xd63b  brfalse.s loc_D656
0xd63d  call     class [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule [System.IdentityModel.Services]System.IdentityModel.Services.FederatedAuthentication::get_SessionAuthenticationModule()
0xd642  castclass Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager
0xd647  call     class [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule [System.IdentityModel.Services]System.IdentityModel.Services.FederatedAuthentication::get_SessionAuthenticationModule()
0xd64c  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_ContextSessionSecurityToken()
0xd651  callvirt instance void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::RemoveSessionTokenFromCache(class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken token)
0xd656  ret
```
