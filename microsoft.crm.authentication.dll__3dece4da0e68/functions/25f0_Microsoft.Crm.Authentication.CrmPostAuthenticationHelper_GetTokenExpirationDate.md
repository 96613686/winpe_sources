# Microsoft.Crm.Authentication.CrmPostAuthenticationHelper::GetTokenExpirationDate

- ea: `0x25f0`
- end: `0x2653`
- name: `Microsoft.Crm.Authentication.CrmPostAuthenticationHelper::GetTokenExpirationDate`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2530`
- `0x2580`
- `0x2a90`

## callees

- `0x25f0`
- `0xe630`

## pseudocode

```c

```

## disassembly

```asm
0x25f0  ldloca.s 0
0x25f2  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x25f8  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x25fd  brfalse.s loc_262C
0x25ff  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2604  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2609  brfalse.s loc_262C
0x260b  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_ClaimsEnabled()
0x2610  brfalse.s loc_262C
0x2612  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x2617  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x261c  isinst   [mscorlib]System.Security.Claims.ClaimsPrincipal
0x2621  stloc.1
0x2622  ldloc.1
0x2623  brfalse.s loc_262C
0x2625  ldloc.1
0x2626  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.Crm.Core]IdentityExtensions::GetCustomSessionTokenValidTo(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x262b  stloc.0
0x262c  ldloca.s 0
0x262e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x2633  brtrue.s loc_2651
0x2635  call     class [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule [System.IdentityModel.Services]System.IdentityModel.Services.FederatedAuthentication::get_SessionAuthenticationModule()
0x263a  brfalse.s loc_2651
0x263c  call     class [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule [System.IdentityModel.Services]System.IdentityModel.Services.FederatedAuthentication::get_SessionAuthenticationModule()
0x2641  isinst   Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager
0x2646  stloc.2
0x2647  ldloc.2
0x2648  brfalse.s loc_2651
0x264a  ldloc.2
0x264b  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::GetSessionTokenExpiration()
0x2650  stloc.0
0x2651  ldloc.0
0x2652  ret
```
