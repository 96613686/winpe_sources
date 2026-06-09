# Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::ValidateToken

- ea: `0xf600`
- end: `0xf644`
- name: `Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::ValidateToken`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xf600`
- `0xf650`

## string_xrefs

- `0xf601`: `token`

## pseudocode

```c

```

## disassembly

```asm
0xf600  ldarg.1
0xf601  ldstr    aToken// "token"
0xf606  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xf60b  ldarg.0
0xf60c  call     instance class [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration Microsoft.Crm.Authentication.Claims.HttpHeaderTokenHandler::get_IdentityConfiguration()
0xf611  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection [System.IdentityModel]System.IdentityModel.Configuration.IdentityConfiguration::get_SecurityTokenHandlers()
0xf616  ldarg.1
0xf617  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Security.Claims.ClaimsIdentity> [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandlerCollection::ValidateToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0xf61c  stloc.0
0xf61d  ldloc.0
0xf61e  call     T0x2B000022
0xf623  isinst   [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity
0xf628  stloc.1
0xf629  ldloc.1
0xf62a  brfalse.s loc_F633
0xf62c  ldloc.1
0xf62d  newobj   instance void [mscorlib]System.Security.Claims.ClaimsPrincipal::.ctor(class [mscorlib]System.Security.Principal.IIdentity)
0xf632  ret
0xf633  ldloc.0
0xf634  call     T0x2B000023
0xf639  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity::Get(class [mscorlib]System.Security.Claims.ClaimsIdentity)
0xf63e  newobj   instance void [mscorlib]System.Security.Claims.ClaimsPrincipal::.ctor(class [mscorlib]System.Security.Principal.IIdentity)
0xf643  ret
```
