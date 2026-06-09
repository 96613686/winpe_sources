# <>c__DisplayClass52_0::<CollectIncomingConnectionType>b__0

- ea: `0xf1d0`
- end: `0xf21d`
- name: `<>c__DisplayClass52_0::<CollectIncomingConnectionType>b__0`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xf1d0`

## pseudocode

```c

```

## disassembly

```asm
0xf1d0  ldarg.1
0xf1d1  ldc.i4.0
0xf1d2  ldelem.ref
0xf1d3  unbox.any [mscorlib]System.Int32
0xf1d8  brtrue.s loc_F1E9
0xf1da  ldarg.0
0xf1db  ldarg.1
0xf1dc  ldc.i4.1
0xf1dd  ldelem.ref
0xf1de  unbox.any [mscorlib]System.Int32
0xf1e3  stfld    int32 <>c__DisplayClass52_0::NumOfIncomingUserSpecifiedEmailServerProfiles
0xf1e8  ret
0xf1e9  ldarg.1
0xf1ea  ldc.i4.0
0xf1eb  ldelem.ref
0xf1ec  unbox.any [mscorlib]System.Int32
0xf1f1  ldc.i4.1
0xf1f2  bne.un.s loc_F203
0xf1f4  ldarg.0
0xf1f5  ldarg.1
0xf1f6  ldc.i4.1
0xf1f7  ldelem.ref
0xf1f8  unbox.any [mscorlib]System.Int32
0xf1fd  stfld    int32 <>c__DisplayClass52_0::NumOfIncomingOtherEmailServerProfiles
0xf202  ret
0xf203  ldarg.1
0xf204  ldc.i4.0
0xf205  ldelem.ref
0xf206  unbox.any [mscorlib]System.Int32
0xf20b  ldc.i4.3
0xf20c  bne.un.s loc_F21C
0xf20e  ldarg.0
0xf20f  ldarg.1
0xf210  ldc.i4.1
0xf211  ldelem.ref
0xf212  unbox.any [mscorlib]System.Int32
0xf217  stfld    int32 <>c__DisplayClass52_0::NumOfIncomingWinIntegratedEmailServerProfiles
0xf21c  ret
```
