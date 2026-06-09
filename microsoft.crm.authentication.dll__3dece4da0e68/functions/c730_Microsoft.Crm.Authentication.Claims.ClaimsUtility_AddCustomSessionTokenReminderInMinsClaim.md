# Microsoft.Crm.Authentication.Claims.ClaimsUtility::AddCustomSessionTokenReminderInMinsClaim

- ea: `0xc730`
- end: `0xc786`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsUtility::AddCustomSessionTokenReminderInMinsClaim`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc6b0`

## callees

- `0xc730`

## string_xrefs

- `0xc76d`: `http://www.w3.org/2001/XMLSchema#integer`

## pseudocode

```c

```

## disassembly

```asm
0xc730  ldarg.0
0xc731  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0xc736  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__52_0
0xc73b  dup
0xc73c  brtrue.s loc_C755
0xc73e  pop
0xc73f  ldsfld   class <>c <>c::<>9
0xc744  ldftn    instance bool <>c::<AddCustomSessionTokenReminderInMinsClaim>b__52_0(class [mscorlib]System.Security.Claims.Claim c)
0xc74a  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool>::.ctor(object, native int)
0xc74f  dup
0xc750  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Security.Claims.Claim, bool> <>c::<>9__52_0
0xc755  call     T0x2B00000D
0xc75a  stloc.0
0xc75b  ldloc.0
0xc75c  brfalse.s loc_C767
0xc75e  ldarg.0
0xc75f  ldloc.0
0xc760  callvirt instance bool [mscorlib]System.Security.Claims.ClaimsIdentity::TryRemoveClaim(class [mscorlib]System.Security.Claims.Claim)
0xc765  brfalse.s loc_C784
0xc767  ldarg.0
0xc768  ldsfld   string [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.ClaimTypes::CustomSessionTokenReminderInMins
0xc76d  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema#intege"...
0xc772  ldarg.1
0xc773  box      [mscorlib]System.Int32
0xc778  call     class [mscorlib]System.Security.Claims.Claim [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.ClaimTypes::CreateClaim(string, string, object)
0xc77d  callvirt instance void [mscorlib]System.Security.Claims.ClaimsIdentity::AddClaim(class [mscorlib]System.Security.Claims.Claim)
0xc782  ldc.i4.1
0xc783  ret
0xc784  ldc.i4.0
0xc785  ret
```
