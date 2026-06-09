# Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::CreateClaimsIdentity

- ea: `0x84b0`
- end: `0x84db`
- name: `Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::CreateClaimsIdentity`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x84b0`
- `0x86c0`
- `0x8820`
- `0xa120`

## pseudocode

```c

```

## disassembly

```asm
0x84b0  ldarg.1
0x84b1  isinst   Microsoft.Crm.Authentication.Claims.ExchangeSecurityToken
0x84b6  stloc.0
0x84b7  ldloc.0
0x84b8  brtrue.s loc_84BC
0x84ba  ldnull
0x84bb  ret
0x84bc  ldloc.0
0x84bd  callvirt instance int32 Microsoft.Crm.Authentication.Claims.ExchangeSecurityToken::get_Version()
0x84c2  ldc.i4.1
0x84c3  bne.un.s loc_84CC
0x84c5  ldarg.1
0x84c6  ldarg.2
0x84c7  call     void Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::MapTokenClaims(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken jwt, string issuer)
0x84cc  ldarg.0
0x84cd  ldarg.1
0x84ce  ldarg.2
0x84cf  ldarg.3
0x84d0  call     instance class [mscorlib]System.Security.Claims.ClaimsIdentity Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::CreateClaimsIdentity(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken jwt, string issuer, class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters validationParameters)
0x84d5  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity::Get(class [mscorlib]System.Security.Claims.ClaimsIdentity)
0x84da  ret
```
