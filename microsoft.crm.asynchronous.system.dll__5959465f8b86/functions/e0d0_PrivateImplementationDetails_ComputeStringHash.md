# <PrivateImplementationDetails>::ComputeStringHash

- ea: `0xe0d0`
- end: `0xe0fc`
- name: `<PrivateImplementationDetails>::ComputeStringHash`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7d60`

## callees

- `0xe0d0`

## pseudocode

```c

```

## disassembly

```asm
0xe0d0  ldarg.0
0xe0d1  brfalse.s loc_E0FA
0xe0d3  ldc.i4   0x811C9DC5
0xe0d8  stloc.0
0xe0d9  ldc.i4.0
0xe0da  stloc.1
0xe0db  br.s     loc_E0F1
0xe0dd  ldarg.0
0xe0de  ldloc.1
0xe0df  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xe0e4  ldloc.0
0xe0e5  xor
0xe0e6  ldc.i4   0x1000193
0xe0eb  mul
0xe0ec  stloc.0
0xe0ed  ldloc.1
0xe0ee  ldc.i4.1
0xe0ef  add
0xe0f0  stloc.1
0xe0f1  ldloc.1
0xe0f2  ldarg.0
0xe0f3  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe0f8  blt.s    loc_E0DD
0xe0fa  ldloc.0
0xe0fb  ret
```
