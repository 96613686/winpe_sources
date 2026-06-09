# Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::ReadToken

- ea: `0xa0e0`
- end: `0xa11f`
- name: `Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::ReadToken`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x8840`
- `0x8870`
- `0xa020`
- `0xa0e0`

## pseudocode

```c

```

## disassembly

```asm
0xa0e0  ldarg.0
0xa0e1  ldarg.1
0xa0e2  call     instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::ReadTokenInternal(string tokenString)
0xa0e7  isinst   [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken
0xa0ec  stloc.0
0xa0ed  ldloc.0
0xa0ee  call     int32 Microsoft.Crm.Authentication.Claims.ExchangeTokenConfig::GetExchangeTokenType(class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken securityToken)
0xa0f3  stloc.1
0xa0f4  ldloc.1
0xa0f5  ldc.i4.0
0xa0f6  ble.s    loc_A11D
0xa0f8  ldloc.1
0xa0f9  ldloc.0
0xa0fa  callvirt instance class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtHeader [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::get_Header()
0xa0ff  ldloc.0
0xa100  callvirt instance class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtPayload [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::get_Payload()
0xa105  ldloc.0
0xa106  callvirt instance string [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::get_RawHeader()
0xa10b  ldloc.0
0xa10c  callvirt instance string [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::get_RawPayload()
0xa111  ldloc.0
0xa112  callvirt instance string [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::get_RawSignature()
0xa117  newobj   instance void Microsoft.Crm.Authentication.Claims.ExchangeSecurityToken::.ctor(int32 version, class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtHeader header, class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtPayload payload, string rawHeader, string rawPayload, string rawSignature)
0xa11c  ret
0xa11d  ldloc.0
0xa11e  ret
```
