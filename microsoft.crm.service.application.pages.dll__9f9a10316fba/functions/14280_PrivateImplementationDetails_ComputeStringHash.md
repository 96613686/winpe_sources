# <PrivateImplementationDetails>::ComputeStringHash

- ea: `0x14280`
- end: `0x142ac`
- name: `<PrivateImplementationDetails>::ComputeStringHash`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa70`

## callees

- `0x14280`

## pseudocode

```c

```

## disassembly

```asm
0x14280  ldarg.0
0x14281  brfalse.s loc_142AA
0x14283  ldc.i4   0x811C9DC5
0x14288  stloc.0
0x14289  ldc.i4.0
0x1428a  stloc.1
0x1428b  br.s     loc_142A1
0x1428d  ldarg.0
0x1428e  ldloc.1
0x1428f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x14294  ldloc.0
0x14295  xor
0x14296  ldc.i4   0x1000193
0x1429b  mul
0x1429c  stloc.0
0x1429d  ldloc.1
0x1429e  ldc.i4.1
0x1429f  add
0x142a0  stloc.1
0x142a1  ldloc.1
0x142a2  ldarg.0
0x142a3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x142a8  blt.s    loc_1428D
0x142aa  ldloc.0
0x142ab  ret
```
