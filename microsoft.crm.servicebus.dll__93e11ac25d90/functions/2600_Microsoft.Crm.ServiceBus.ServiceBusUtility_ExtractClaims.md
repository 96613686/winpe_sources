# Microsoft.Crm.ServiceBus.ServiceBusUtility::ExtractClaims

- ea: `0x2600`
- end: `0x265d`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::ExtractClaims`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x4450`

## callees

- `0x2600`
- `0x2660`

## string_xrefs

- `0x2601`: `tokenString`
- `0x2611`: `Token`
- `0x261e`: `Invalid Token`
- `0x2645`: `Invalid Token Format`

## pseudocode

```c

```

## disassembly

```asm
0x2600  ldarg.0
0x2601  ldstr    aTokenstring// "tokenString"
0x2606  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x260b  ldarg.0
0x260c  callvirt instance string [mscorlib]System.String::Trim()
0x2611  ldstr    aToken// "Token"
0x2616  ldc.i4.5
0x2617  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x261c  brtrue.s loc_262E
0x261e  ldstr    aInvalidToken// "Invalid Token"
0x2623  ldc.i4   0x80044178
0x2628  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x262d  throw
0x262e  ldarg.0
0x262f  ldc.i4.1
0x2630  newarr   [mscorlib]System.Char
0x2635  dup
0x2636  ldc.i4.0
0x2637  ldc.i4.s 0x20
0x2639  stelem.i2
0x263a  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x263f  dup
0x2640  ldlen
0x2641  conv.i4
0x2642  ldc.i4.2
0x2643  beq.s    loc_2655
0x2645  ldstr    aInvalidTokenFo// "Invalid Token Format"
0x264a  ldc.i4   0x80044178
0x264f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2654  throw
0x2655  ldc.i4.1
0x2656  ldelem.ref
0x2657  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ServiceBus.ServiceBusUtility::GetNameValues(string token)
0x265c  ret
```
