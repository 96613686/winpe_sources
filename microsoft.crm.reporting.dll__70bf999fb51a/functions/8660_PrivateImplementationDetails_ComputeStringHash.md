# <PrivateImplementationDetails>::ComputeStringHash

- ea: `0x8660`
- end: `0x868c`
- name: `<PrivateImplementationDetails>::ComputeStringHash`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x19f0`

## callees

- `0x8660`

## pseudocode

```c

```

## disassembly

```asm
0x8660  ldarg.0
0x8661  brfalse.s loc_868A
0x8663  ldc.i4   0x811C9DC5
0x8668  stloc.0
0x8669  ldc.i4.0
0x866a  stloc.1
0x866b  br.s     loc_8681
0x866d  ldarg.0
0x866e  ldloc.1
0x866f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x8674  ldloc.0
0x8675  xor
0x8676  ldc.i4   0x1000193
0x867b  mul
0x867c  stloc.0
0x867d  ldloc.1
0x867e  ldc.i4.1
0x867f  add
0x8680  stloc.1
0x8681  ldloc.1
0x8682  ldarg.0
0x8683  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8688  blt.s    loc_866D
0x868a  ldloc.0
0x868b  ret
```
