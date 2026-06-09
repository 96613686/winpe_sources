# <>c__DisplayClass55_0::<CollectIncomingAndOutgoingAccessType>b__0

- ea: `0xf300`
- end: `0xf319`
- name: `<>c__DisplayClass55_0::<CollectIncomingAndOutgoingAccessType>b__0`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xf300`

## pseudocode

```c

```

## disassembly

```asm
0xf300  ldarg.1
0xf301  ldc.i4.0
0xf302  ldelem.ref
0xf303  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xf308  beq.s    loc_F318
0xf30a  ldarg.0
0xf30b  ldarg.1
0xf30c  ldc.i4.0
0xf30d  ldelem.ref
0xf30e  unbox.any [mscorlib]System.Int32
0xf313  stfld    int32 <>c__DisplayClass55_0::NumOfIncomingImpersonationTypeProfile
0xf318  ret
```
