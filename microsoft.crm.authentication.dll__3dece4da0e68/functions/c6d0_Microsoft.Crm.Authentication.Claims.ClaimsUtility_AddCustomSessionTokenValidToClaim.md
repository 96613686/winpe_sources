# Microsoft.Crm.Authentication.Claims.ClaimsUtility::AddCustomSessionTokenValidToClaim

- ea: `0xc6d0`
- end: `0xc726`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsUtility::AddCustomSessionTokenValidToClaim`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc6b0`

## callees

- `0xc6d0`

## string_xrefs

- `0xc70d`: `http://www.w3.org/2001/XMLSchema#dateTime`

## pseudocode

```c

```

## disassembly

```asm
0xc6d0  ldarg.0
0xc6d1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0xc6d6  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__51_0
0xc6db  dup
0xc6dc  brtrue.s loc_C6F5
0xc6de  pop
0xc6df  ldsfld   class <>c <>c::<>9
0xc6e4  ldftn    instance bool <>c::<AddCustomSessionTokenValidToClaim>b__51_0(class [mscorlib]System.Security.Claims.Claim c)
0xc6ea  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0xc6ef  dup
0xc6f0  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__51_0
0xc6f5  call     T0x2B00000D
0xc6fa  stloc.0
0xc6fb  ldloc.0
0xc6fc  brfalse.s loc_C707
0xc6fe  ldarg.0
0xc6ff  ldloc.0
0xc700  callvirt instance bool [mscorlib]System.Security.Claims.ClaimsIdentity::TryRemoveClaim(class [mscorlib]System.Security.Claims.Claim)
0xc705  brfalse.s loc_C724
0xc707  ldarg.0
0xc708  ldsfld   string [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.ClaimTypes::CustomSessionTokenValidTo
0xc70d  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema#dateTi"...
0xc712  ldarg.1
0xc713  box      [mscorlib]System.DateTime
0xc718  call     class [mscorlib]System.Security.Claims.Claim [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.ClaimTypes::CreateClaim(string, string, object)
0xc71d  callvirt instance void [mscorlib]System.Security.Claims.ClaimsIdentity::AddClaim(class [mscorlib]System.Security.Claims.Claim)
0xc722  ldc.i4.1
0xc723  ret
0xc724  ldc.i4.0
0xc725  ret
```
