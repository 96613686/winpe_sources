# Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::ValidateCustomAudience

- ea: `0x84e0`
- end: `0x8540`
- name: `Microsoft.Crm.Authentication.Claims.ExchangeJwtSecurityTokenHandler::ValidateCustomAudience`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x84e0`
- `0x8820`
- `0x8910`
- `0x89a0`
- `0x14680`

## pseudocode

```c

```

## disassembly

```asm
0x84e0  ldarg.2
0x84e1  brtrue.s loc_84E5
0x84e3  ldc.i4.0
0x84e4  ret
0x84e5  ldarg.1
0x84e6  isinst   Microsoft.Crm.Authentication.Claims.ExchangeSecurityToken
0x84eb  stloc.0
0x84ec  ldloc.0
0x84ed  brtrue.s loc_84F1
0x84ef  ldc.i4.0
0x84f0  ret
0x84f1  ldloc.0
0x84f2  callvirt instance int32 Microsoft.Crm.Authentication.Claims.ExchangeSecurityToken::get_Version()
0x84f7  ldc.i4.1
0x84f8  bne.un.s loc_853E
0x84fa  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x84ff  stloc.1
0x8500  ldloc.1
0x8501  ldarg.2
0x8502  call     T0x2B00000E
0x8507  call     class Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer::Get(string tokenAudience)
0x850c  stfld    class Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer <>c__DisplayClass5_0::tokenIssuer
0x8511  ldloc.1
0x8512  ldfld    class Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer <>c__DisplayClass5_0::tokenIssuer
0x8517  brfalse.s loc_853E
0x8519  ldloc.1
0x851a  ldfld    class Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer <>c__DisplayClass5_0::tokenIssuer
0x851f  callvirt instance string Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer::get_Issuer()
0x8524  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8529  brtrue.s loc_853E
0x852b  ldarg.3
0x852c  ldloc.1
0x852d  ldftn    instance bool <>c__DisplayClass5_0::<ValidateCustomAudience>b__0(string issuer)
0x8533  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x8538  call     T0x2B00000F
0x853d  ret
0x853e  ldc.i4.0
0x853f  ret
```
