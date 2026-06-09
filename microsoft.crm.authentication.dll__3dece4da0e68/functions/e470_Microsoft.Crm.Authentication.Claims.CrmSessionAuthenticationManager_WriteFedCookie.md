# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::WriteFedCookie

- ea: `0xe470`
- end: `0xe4f7`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::WriteFedCookie`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xe510`

## callees

- `0x2d50`
- `0x2e20`
- `0xe470`
- `0xe6e0`

## pseudocode

```c

```

## disassembly

```asm
0xe470  ldarg.0
0xe471  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe476  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_Domain()
0xe47b  stloc.0
0xe47c  ldarg.0
0xe47d  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe482  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_Path()
0xe487  stloc.1
0xe488  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAppUtilSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.AppUtilSettingsProvider::get_Instance()
0xe48d  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IAppUtilSettingsProvider::IsPathBasedURLsEnabled()
0xe492  brtrue.s loc_E4B9
0xe494  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe499  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xe49e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xe4a3  ldc.i4.2
0xe4a4  beq.s    loc_E4A9
0xe4a6  ldloc.0
0xe4a7  br.s     loc_E4B3
0xe4a9  call     class Microsoft.Crm.Authentication.CrmPostAuthenticationSettings Microsoft.Crm.Authentication.CrmPostAuthenticationSettings::get_Instance()
0xe4ae  callvirt instance string Microsoft.Crm.Authentication.CrmPostAuthenticationSettings::get_Domain()
0xe4b3  call     string Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::GetIFDDomain(valuetype [mscorlib]System.Guid orgId, string domain)
0xe4b8  stloc.0
0xe4b9  ldarg.1
0xe4ba  newobj   instance void [System.Web]System.Web.HttpCookie::.ctor(string)
0xe4bf  stloc.2
0xe4c0  ldloc.2
0xe4c1  ldloc.1
0xe4c2  callvirt instance void [System.Web]System.Web.HttpCookie::set_Path(string)
0xe4c7  ldloc.2
0xe4c8  ldloc.0
0xe4c9  callvirt instance void [System.Web]System.Web.HttpCookie::set_Domain(string)
0xe4ce  ldloc.2
0xe4cf  ldarg.0
0xe4d0  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe4d5  callvirt instance bool [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_HideFromClientScript()
0xe4da  callvirt instance void [System.Web]System.Web.HttpCookie::set_HttpOnly(bool)
0xe4df  ldloc.2
0xe4e0  ldc.i4.1
0xe4e1  callvirt instance void [System.Web]System.Web.HttpCookie::set_Secure(bool)
0xe4e6  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe4eb  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0xe4f0  ldloc.2
0xe4f1  callvirt instance void [System.Web]System.Web.HttpResponse::AppendCookie(class [System.Web]System.Web.HttpCookie)
0xe4f6  ret
```
