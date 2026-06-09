# Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer::Get

- ea: `0x8910`
- end: `0x899e`
- name: `Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer::Get`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x84e0`

## callees

- `0x8900`
- `0x8910`
- `0x89b0`
- `0x89d0`
- `0x89f0`
- `0xddd0`

## pseudocode

```c

```

## disassembly

```asm
0x8910  ldarg.0
0x8911  ldc.i4.1
0x8912  newarr   [mscorlib]System.Char
0x8917  dup
0x8918  ldc.i4.0
0x8919  ldc.i4.s 0x40
0x891b  stelem.i2
0x891c  ldc.i4.1
0x891d  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x8922  stloc.0
0x8923  ldloc.0
0x8924  ldlen
0x8925  conv.i4
0x8926  ldc.i4.2
0x8927  beq.s    loc_892B
0x8929  ldnull
0x892a  ret
0x892b  newobj   instance void Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer::.ctor()
0x8930  stloc.1
0x8931  ldloc.0
0x8932  ldc.i4.0
0x8933  ldelem.ref
0x8934  ldc.i4.s 0x2F
0x8936  call     T0x2B000011
0x893b  brfalse.s loc_8976
0x893d  ldloc.0
0x893e  ldc.i4.0
0x893f  ldelem.ref
0x8940  ldc.i4.1
0x8941  newarr   [mscorlib]System.Char
0x8946  dup
0x8947  ldc.i4.0
0x8948  ldc.i4.s 0x2F
0x894a  stelem.i2
0x894b  ldc.i4.1
0x894c  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x8951  stloc.3
0x8952  ldloc.3
0x8953  ldlen
0x8954  conv.i4
0x8955  ldc.i4.1
0x8956  blt.s    loc_8989
0x8958  ldloc.1
0x8959  ldloc.3
0x895a  ldc.i4.1
0x895b  ldelem.ref
0x895c  callvirt instance void Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer::set_IssuerName(string value)
0x8961  ldloc.1
0x8962  ldloc.3
0x8963  ldc.i4.0
0x8964  ldelem.ref
0x8965  call     class [System]System.Uri Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::CreateSpnPrefixAudience(string audience)
0x896a  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x896f  callvirt instance void Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer::set_Issuer(string value)
0x8974  br.s     loc_8989
0x8976  ldloc.1
0x8977  ldloc.0
0x8978  ldc.i4.0
0x8979  ldelem.ref
0x897a  call     class [System]System.Uri Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::CreateSpnPrefixAudience(string audience)
0x897f  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x8984  callvirt instance void Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer::set_Issuer(string value)
0x8989  ldloc.0
0x898a  ldc.i4.1
0x898b  ldelem.ref
0x898c  ldloca.s 2
0x898e  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x8993  brfalse.s loc_899C
0x8995  ldloc.1
0x8996  ldloc.2
0x8997  callvirt instance void Microsoft.Crm.Authentication.Claims.ExchangeTokenIssuer::set_TenantId(valuetype [mscorlib]System.Guid value)
0x899c  ldloc.1
0x899d  ret
```
