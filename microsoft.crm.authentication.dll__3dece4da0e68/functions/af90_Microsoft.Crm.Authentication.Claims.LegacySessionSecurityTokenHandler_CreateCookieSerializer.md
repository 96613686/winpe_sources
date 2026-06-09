# Microsoft.Crm.Authentication.Claims.LegacySessionSecurityTokenHandler::CreateCookieSerializer

- ea: `0xaf90`
- end: `0xafe1`
- name: `Microsoft.Crm.Authentication.Claims.LegacySessionSecurityTokenHandler::CreateCookieSerializer`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xade0`

## callees

- `0xaf90`
- `0x11610`

## pseudocode

```c

```

## disassembly

```asm
0xaf90  ldarg.0
0xaf91  call     instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler::get_ContainingCollection()
0xaf96  dup
0xaf97  brtrue.s loc_AF9F
0xaf99  pop
0xaf9a  call     class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::CreateDefaultSecurityTokenHandlerCollection()
0xaf9f  ldc.i4.0
0xafa0  stloc.0
0xafa1  ldstr    aLocalAuthority// "LOCAL AUTHORITY"
0xafa6  stloc.1
0xafa7  ldarg.0
0xafa8  call     instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler::get_Configuration()
0xafad  brfalse.s loc_AFCC
0xafaf  ldarg.0
0xafb0  call     instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler::get_Configuration()
0xafb5  callvirt instance bool [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration::get_SaveBootstrapContext()
0xafba  stloc.0
0xafbb  ldarg.0
0xafbc  call     instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler::get_Configuration()
0xafc1  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.IssuerNameRegistry [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration::get_IssuerNameRegistry()
0xafc6  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.IssuerNameRegistry::GetWindowsIssuerName()
0xafcb  stloc.1
0xafcc  ldloca.s 0
0xafce  call     instance string [mscorlib]System.Boolean::ToString()
0xafd3  pop
0xafd4  ldloc.1
0xafd5  callvirt instance string [mscorlib]System.Object::ToString()
0xafda  pop
0xafdb  newobj   instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifSecurityTokenCookieSerializer::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection bootstrapTokenHandlers)
0xafe0  ret
```
