# Microsoft.Crm.Transformations.Substring::Evaluate

- ea: `0x23e0`
- end: `0x256f`
- name: `Microsoft.Crm.Transformations.Substring::Evaluate`
- size: `399`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x23e0`

## pseudocode

```c

```

## disassembly

```asm
0x23e0  ldarg.1
0x23e1  brfalse.s loc_23E9
0x23e3  ldarg.1
0x23e4  ldlen
0x23e5  conv.i4
0x23e6  ldc.i4.3
0x23e7  beq.s    loc_23FA
0x23e9  ldc.i4   0x80048506
0x23ee  ldc.i4.0
0x23ef  newarr   [mscorlib]System.Object
0x23f4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23f9  throw
0x23fa  ldnull
0x23fb  stloc.0
0x23fc  ldarg.1
0x23fd  ldc.i4.0
0x23fe  ldelem.ref
0x23ff  isinst   [mscorlib]System.String
0x2404  brtrue.s loc_242D
0x2406  ldc.i4   0x80048507
0x240b  ldc.i4.3
0x240c  newarr   [mscorlib]System.Object
0x2411  dup
0x2412  ldc.i4.0
0x2413  ldstr    a1// "1"
0x2418  stelem.ref
0x2419  dup
0x241a  ldc.i4.1
0x241b  ldarg.1
0x241c  ldc.i4.0
0x241d  ldelem.ref
0x241e  stelem.ref
0x241f  dup
0x2420  ldc.i4.2
0x2421  ldstr    aString// "String"
0x2426  stelem.ref
0x2427  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x242c  throw
0x242d  ldarg.1
0x242e  ldc.i4.0
0x242f  ldelem.ref
0x2430  castclass [mscorlib]System.String
0x2435  dup
0x2436  stloc.0
0x2437  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x243c  brfalse.s loc_245D
0x243e  ldc.i4   0x80048508
0x2443  ldc.i4.2
0x2444  newarr   [mscorlib]System.Object
0x2449  dup
0x244a  ldc.i4.0
0x244b  ldstr    a1// "1"
0x2450  stelem.ref
0x2451  dup
0x2452  ldc.i4.1
0x2453  ldarg.1
0x2454  ldc.i4.0
0x2455  ldelem.ref
0x2456  stelem.ref
0x2457  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x245c  throw
0x245d  ldarg.1
0x245e  ldc.i4.1
0x245f  ldelem.ref
0x2460  isinst   [mscorlib]System.Int32
0x2465  brtrue.s loc_248E
0x2467  ldc.i4   0x80048507
0x246c  ldc.i4.3
0x246d  newarr   [mscorlib]System.Object
0x2472  dup
0x2473  ldc.i4.0
0x2474  ldstr    a2// "2"
0x2479  stelem.ref
0x247a  dup
0x247b  ldc.i4.1
0x247c  ldarg.1
0x247d  ldc.i4.0
0x247e  ldelem.ref
0x247f  stelem.ref
0x2480  dup
0x2481  ldc.i4.2
0x2482  ldstr    aInteger// "Integer"
0x2487  stelem.ref
0x2488  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x248d  throw
0x248e  ldarg.1
0x248f  ldc.i4.1
0x2490  ldelem.ref
0x2491  unbox.any [mscorlib]System.Int32
0x2496  stloc.1
0x2497  ldloc.1
0x2498  ldc.i4.0
0x2499  blt.s    loc_24A4
0x249b  ldloc.1
0x249c  ldloc.0
0x249d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x24a2  blt.s    loc_24C3
0x24a4  ldc.i4   0x80048509
0x24a9  ldc.i4.2
0x24aa  newarr   [mscorlib]System.Object
0x24af  dup
0x24b0  ldc.i4.0
0x24b1  ldstr    a2// "2"
0x24b6  stelem.ref
0x24b7  dup
0x24b8  ldc.i4.1
0x24b9  ldarg.1
0x24ba  ldc.i4.0
0x24bb  ldelem.ref
0x24bc  stelem.ref
0x24bd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x24c2  throw
0x24c3  ldarg.1
0x24c4  ldc.i4.2
0x24c5  ldelem.ref
0x24c6  brfalse  loc_255E
0x24cb  ldarg.1
0x24cc  ldc.i4.2
0x24cd  ldelem.ref
0x24ce  isinst   [mscorlib]System.Int32
0x24d3  brtrue.s loc_24FC
0x24d5  ldc.i4   0x80048507
0x24da  ldc.i4.3
0x24db  newarr   [mscorlib]System.Object
0x24e0  dup
0x24e1  ldc.i4.0
0x24e2  ldstr    a3// "3"
0x24e7  stelem.ref
0x24e8  dup
0x24e9  ldc.i4.1
0x24ea  ldarg.1
0x24eb  ldc.i4.0
0x24ec  ldelem.ref
0x24ed  stelem.ref
0x24ee  dup
0x24ef  ldc.i4.2
0x24f0  ldstr    aInteger// "Integer"
0x24f5  stelem.ref
0x24f6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x24fb  throw
0x24fc  ldarg.1
0x24fd  ldc.i4.2
0x24fe  ldelem.ref
0x24ff  unbox.any [mscorlib]System.Int32
0x2504  stloc.2
0x2505  ldloc.2
0x2506  ldc.i4.0
0x2507  bgt.s    loc_2530
0x2509  ldc.i4   0x80048507
0x250e  ldc.i4.3
0x250f  newarr   [mscorlib]System.Object
0x2514  dup
0x2515  ldc.i4.0
0x2516  ldstr    a3// "3"
0x251b  stelem.ref
0x251c  dup
0x251d  ldc.i4.1
0x251e  ldarg.1
0x251f  ldc.i4.0
0x2520  ldelem.ref
0x2521  stelem.ref
0x2522  dup
0x2523  ldc.i4.2
0x2524  ldstr    aInteger// "Integer"
0x2529  stelem.ref
0x252a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x252f  throw
0x2530  ldloc.2
0x2531  ldloc.1
0x2532  add
0x2533  ldloc.0
0x2534  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2539  blt.s    loc_254C
0x253b  ldc.i4.1
0x253c  newarr   [mscorlib]System.Object
0x2541  dup
0x2542  ldc.i4.0
0x2543  ldloc.0
0x2544  ldloc.1
0x2545  callvirt instance string [mscorlib]System.String::Substring(int32)
0x254a  stelem.ref
0x254b  ret
0x254c  ldc.i4.1
0x254d  newarr   [mscorlib]System.Object
0x2552  dup
0x2553  ldc.i4.0
0x2554  ldloc.0
0x2555  ldloc.1
0x2556  ldloc.2
0x2557  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x255c  stelem.ref
0x255d  ret
0x255e  ldc.i4.1
0x255f  newarr   [mscorlib]System.Object
0x2564  dup
0x2565  ldc.i4.0
0x2566  ldloc.0
0x2567  ldloc.1
0x2568  callvirt instance string [mscorlib]System.String::Substring(int32)
0x256d  stelem.ref
0x256e  ret
```
