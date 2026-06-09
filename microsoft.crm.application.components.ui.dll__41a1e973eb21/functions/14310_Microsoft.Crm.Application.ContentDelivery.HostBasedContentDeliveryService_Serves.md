# Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::Serves

- ea: `0x14310`
- end: `0x143a4`
- name: `Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::Serves`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3e30`

## callees

- `0x142c0`
- `0x14310`

## string_xrefs

- `0x1432c`: `relativeUri`
- `0x14344`: `relativeUri`
- `0x1433f`: `Uri must be relative`

## pseudocode

```c

```

## disassembly

```asm
0x14310  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x14315  ldsfld   string [mscorlib]System.String::Empty
0x1431a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1431f  brfalse.s loc_14323
0x14321  ldc.i4.0
0x14322  ret
0x14323  ldarg.0
0x14324  ldnull
0x14325  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x1432a  brfalse.s loc_14337
0x1432c  ldstr    aRelativeuri// "relativeUri"
0x14331  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14336  throw
0x14337  ldarg.0
0x14338  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x1433d  brfalse.s loc_1434F
0x1433f  ldstr    aUriMustBeRelat// "Uri must be relative"
0x14344  ldstr    aRelativeuri// "relativeUri"
0x14349  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1434e  throw
0x1434f  ldarg.0
0x14350  callvirt instance string [System]System.Uri::get_OriginalString()
0x14355  ldc.i4.1
0x14356  newarr   [mscorlib]System.Char
0x1435b  dup
0x1435c  ldc.i4.0
0x1435d  ldc.i4.s 0x3F
0x1435f  stelem.i2
0x14360  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x14365  ldc.i4.0
0x14366  ldelem.ref
0x14367  stloc.0
0x14368  ldloc.0
0x14369  ldstr    aStatic// "/_static/"
0x1436e  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x14373  brfalse.s loc_143A2
0x14375  ldloc.0
0x14376  ldstr    aJs// ".js"
0x1437b  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x14380  brtrue.s loc_143A0
0x14382  ldloc.0
0x14383  ldstr    aCss// ".css"
0x14388  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1438d  brfalse.s loc_1439E
0x1438f  ldloc.0
0x14390  ldstr    aAspx// ".aspx"
0x14395  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x1439a  ldc.i4.0
0x1439b  ceq
0x1439d  ret
0x1439e  ldc.i4.0
0x1439f  ret
0x143a0  ldc.i4.1
0x143a1  ret
0x143a2  ldc.i4.0
0x143a3  ret
```
