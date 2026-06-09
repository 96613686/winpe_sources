# Microsoft.Crm.ScaleGroupApi.TokenAudienceValidator::AudienceValidator

- ea: `0xd70`
- end: `0xd9f`
- name: `Microsoft.Crm.ScaleGroupApi.TokenAudienceValidator::AudienceValidator`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xd70`
- `0x51c0`

## pseudocode

```c

```

## disassembly

```asm
0xd70  newobj   instance void <>c__DisplayClass0_0::.ctor()
0xd75  stloc.0
0xd76  ldloc.0
0xd77  ldarg.0
0xd78  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass0_0::audiences
0xd7d  ldarg.1
0xd7e  isinst   [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.JwtSecurityToken
0xd83  brtrue.s loc_D87
0xd85  ldc.i4.0
0xd86  ret
0xd87  ldarg.2
0xd88  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [System.IdentityModel.Tokens.Jwt]System.IdentityModel.Tokens.TokenValidationParameters::get_ValidAudiences()
0xd8d  ldloc.0
0xd8e  ldftn    instance bool <>c__DisplayClass0_0::<AudienceValidator>b__0(string audience)
0xd94  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xd99  call     T0x2B00000B
0xd9e  ret
```
