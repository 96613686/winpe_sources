# <>c__DisplayClass55_0::<CollectIncomingAndOutgoingAccessType>b__1

- ea: `0xf320`
- end: `0xf359`
- name: `<>c__DisplayClass55_0::<CollectIncomingAndOutgoingAccessType>b__1`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xf320`

## pseudocode

```c

```

## disassembly

```asm
0xf320  ldarg.1
0xf321  ldc.i4.0
0xf322  ldelem.ref
0xf323  unbox.any [mscorlib]System.Boolean
0xf328  brfalse.s loc_F340
0xf32a  ldarg.0
0xf32b  ldarg.0
0xf32c  ldfld    int32 <>c__DisplayClass55_0::NumOfOutgoingImpersonationTypeProfile
0xf331  ldarg.1
0xf332  ldc.i4.2
0xf333  ldelem.ref
0xf334  unbox.any [mscorlib]System.Int32
0xf339  add
0xf33a  stfld    int32 <>c__DisplayClass55_0::NumOfOutgoingImpersonationTypeProfile
0xf33f  ret
0xf340  ldarg.1
0xf341  ldc.i4.1
0xf342  ldelem.ref
0xf343  unbox.any [mscorlib]System.Boolean
0xf348  brfalse.s loc_F358
0xf34a  ldarg.0
0xf34b  ldarg.1
0xf34c  ldc.i4.2
0xf34d  ldelem.ref
0xf34e  unbox.any [mscorlib]System.Int32
0xf353  stfld    int32 <>c__DisplayClass55_0::NumOfOutgoingAutoGrantDelegateAccessTypeProfile
0xf358  ret
```
