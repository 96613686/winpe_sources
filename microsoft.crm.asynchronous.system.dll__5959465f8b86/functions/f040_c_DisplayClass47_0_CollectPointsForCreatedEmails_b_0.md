# <>c__DisplayClass47_0::<CollectPointsForCreatedEmails>b__0

- ea: `0xf040`
- end: `0xf073`
- name: `<>c__DisplayClass47_0::<CollectPointsForCreatedEmails>b__0`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xf040`

## pseudocode

```c

```

## disassembly

```asm
0xf040  ldarg.1
0xf041  ldc.i4.0
0xf042  ldelem.ref
0xf043  unbox.any [mscorlib]System.Int32
0xf048  brtrue.s loc_F059
0xf04a  ldarg.0
0xf04b  ldarg.1
0xf04c  ldc.i4.1
0xf04d  ldelem.ref
0xf04e  unbox.any [mscorlib]System.Int32
0xf053  stfld    int32 <>c__DisplayClass47_0::NumOfBulkEmailsCreatedPerDay
0xf058  ret
0xf059  ldarg.1
0xf05a  ldc.i4.0
0xf05b  ldelem.ref
0xf05c  unbox.any [mscorlib]System.Int32
0xf061  ldc.i4.1
0xf062  bne.un.s loc_F072
0xf064  ldarg.0
0xf065  ldarg.1
0xf066  ldc.i4.1
0xf067  ldelem.ref
0xf068  unbox.any [mscorlib]System.Int32
0xf06d  stfld    int32 <>c__DisplayClass47_0::NumOfEmailsCreatedPerDay
0xf072  ret
```
