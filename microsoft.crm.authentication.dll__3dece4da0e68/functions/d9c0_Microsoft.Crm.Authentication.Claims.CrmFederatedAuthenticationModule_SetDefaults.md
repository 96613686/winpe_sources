# Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::SetDefaults

- ea: `0xd9c0`
- end: `0xd9e3`
- name: `Microsoft.Crm.Authentication.Claims.CrmFederatedAuthenticationModule::SetDefaults`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xdab0`

## string_xrefs

- `0xd9c0`: `uri:placeholder`

## pseudocode

```c

```

## disassembly

```asm
0xd9c0  ldstr    aUriPlaceholder// "uri:placeholder"
0xd9c5  stloc.0
0xd9c6  ldarg.0
0xd9c7  ldloc.0
0xd9c8  call     instance void [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationAuthenticationModule::set_Realm(string)
0xd9cd  ldarg.0
0xd9ce  ldloc.0
0xd9cf  call     instance void [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationAuthenticationModule::set_Issuer(string)
0xd9d4  ldarg.0
0xd9d5  ldc.i4.1
0xd9d6  call     instance void [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationAuthenticationModule::set_PassiveRedirectEnabled(bool)
0xd9db  ldarg.0
0xd9dc  ldc.i4.1
0xd9dd  call     instance void [System.IdentityModel.Services]System.IdentityModel.Services.WSFederationAuthenticationModule::set_RequireHttps(bool)
0xd9e2  ret
```
