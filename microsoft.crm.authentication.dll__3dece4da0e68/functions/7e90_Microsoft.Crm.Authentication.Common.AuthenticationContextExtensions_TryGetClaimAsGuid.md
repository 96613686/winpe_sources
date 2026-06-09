# Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::TryGetClaimAsGuid

- ea: `0x7e90`
- end: `0x7ed8`
- name: `Microsoft.Crm.Authentication.Common.AuthenticationContextExtensions::TryGetClaimAsGuid`
- size: `72`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x7e30`
- `0x7e50`
- `0x7e70`

## callees

- `0x7e90`
- `0x14600`

## pseudocode

```c

```

## disassembly

```asm
0x7e90  newobj   instance void <>c__DisplayClass8_0::.ctor()
0x7e95  stloc.0
0x7e96  ldloc.0
0x7e97  ldarg.1
0x7e98  stfld    string <>c__DisplayClass8_0::claimType
0x7e9d  ldarg.2
0x7e9e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7ea3  stobj    [mscorlib]System.Guid
0x7ea8  ldarg.0
0x7ea9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken::get_Claims()
0x7eae  ldloc.0
0x7eaf  ldftn    instance bool <>c__DisplayClass8_0::<TryGetClaimAsGuid>b__0(class [mscorlib]System.Security.Claims.Claim c)
0x7eb5  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0x7eba  call     T0x2B00000D
0x7ebf  stloc.1
0x7ec0  ldloc.1
0x7ec1  brtrue.s loc_7EC5
0x7ec3  ldc.i4.0
0x7ec4  ret
0x7ec5  ldarg.2
0x7ec6  ldloc.1
0x7ec7  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x7ecc  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x7ed1  stobj    [mscorlib]System.Guid
0x7ed6  ldc.i4.1
0x7ed7  ret
```
