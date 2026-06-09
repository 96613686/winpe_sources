# Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::MapTokenClaims

- ea: `0x86c0`
- end: `0x878b`
- name: `Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::MapTokenClaims`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x84b0`

## callees

- `0x86c0`
- `0x8790`

## string_xrefs

- `0x86d4`: `The token does not include a tenant id claim!`
- `0x872e`: `The token does not include an appctx claim!`

## pseudocode

```c

```

## disassembly

```asm
0x86c0  ldarg.1
0x86c1  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::GetTenantId(string tokenIssuer)
0x86c6  stloc.0
0x86c7  ldloc.0
0x86c8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x86cd  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x86d2  brfalse.s loc_86DF
0x86d4  ldstr    aTheTokenDoesNo// "The token does not include a tenant id "...
0x86d9  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x86de  throw
0x86df  ldarg.0
0x86e0  callvirt instance class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtPayload [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::get_Payload()
0x86e5  ldstr    aTid// "tid"
0x86ea  ldloca.s 0
0x86ec  constrained. [mscorlib]System.Guid
0x86f2  callvirt instance string [mscorlib]System.Object::ToString()
0x86f7  newobj   instance void [mscorlib]System.Security.Claims.Claim::.ctor(string, string)
0x86fc  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtPayload::AddClaim(class [mscorlib]System.Security.Claims.Claim)
0x8701  ldarg.0
0x8702  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::get_Claims()
0x8707  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__8_0
0x870c  dup
0x870d  brtrue.s loc_8726
0x870f  pop
0x8710  ldsfld   class <>c <>c::<>9
0x8715  ldftn    instance bool <>c::<MapTokenClaims>b__8_0(class [mscorlib]System.Security.Claims.Claim c)
0x871b  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0x8720  dup
0x8721  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__8_0
0x8726  call     T0x2B00000D
0x872b  dup
0x872c  brtrue.s loc_8739
0x872e  ldstr    aTheTokenDoesNo_0// "The token does not include an appctx cl"...
0x8733  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x8738  throw
0x8739  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x873e  call     T0x2B000010
0x8743  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x8748  stloc.1
0x8749  br.s     loc_8771
0x874b  ldloca.s 1
0x874d  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x8752  stloc.2
0x8753  ldarg.0
0x8754  callvirt instance class [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtPayload [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::get_Payload()
0x8759  ldloca.s 2
0x875b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x8760  ldloca.s 2
0x8762  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x8767  newobj   instance void [mscorlib]System.Security.Claims.Claim::.ctor(string, string)
0x876c  callvirt instance void [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtPayload::AddClaim(class [mscorlib]System.Security.Claims.Claim)
0x8771  ldloca.s 1
0x8773  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x8778  brtrue.s loc_874B
0x877a  leave.s  loc_878A
0x877c  ldloca.s 1
0x877e  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x8784  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8789  endfinally
0x878a  ret
```
