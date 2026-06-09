# <PrivateImplementationDetails>::ComputeStringHash

- ea: `0x4170`
- end: `0x419c`
- name: `<PrivateImplementationDetails>::ComputeStringHash`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1240`

## callees

- `0x4170`

## pseudocode

```c

```

## disassembly

```asm
0x4170  ldarg.0
0x4171  brfalse.s loc_419A
0x4173  ldc.i4   0x811C9DC5
0x4178  stloc.0
0x4179  ldc.i4.0
0x417a  stloc.1
0x417b  br.s     loc_4191
0x417d  ldarg.0
0x417e  ldloc.1
0x417f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x4184  ldloc.0
0x4185  xor
0x4186  ldc.i4   0x1000193
0x418b  mul
0x418c  stloc.0
0x418d  ldloc.1
0x418e  ldc.i4.1
0x418f  add
0x4190  stloc.1
0x4191  ldloc.1
0x4192  ldarg.0
0x4193  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4198  blt.s    loc_417D
0x419a  ldloc.0
0x419b  ret
```
