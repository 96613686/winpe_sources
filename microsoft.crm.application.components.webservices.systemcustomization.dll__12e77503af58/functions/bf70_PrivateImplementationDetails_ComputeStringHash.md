# <PrivateImplementationDetails>::ComputeStringHash

- ea: `0xbf70`
- end: `0xbf9c`
- name: `<PrivateImplementationDetails>::ComputeStringHash`
- size: `44`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x430`
- `0x1bd0`
- `0x7780`

## callees

- `0xbf70`

## pseudocode

```c

```

## disassembly

```asm
0xbf70  ldarg.0
0xbf71  brfalse.s loc_BF9A
0xbf73  ldc.i4   0x811C9DC5
0xbf78  stloc.0
0xbf79  ldc.i4.0
0xbf7a  stloc.1
0xbf7b  br.s     loc_BF91
0xbf7d  ldarg.0
0xbf7e  ldloc.1
0xbf7f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xbf84  ldloc.0
0xbf85  xor
0xbf86  ldc.i4   0x1000193
0xbf8b  mul
0xbf8c  stloc.0
0xbf8d  ldloc.1
0xbf8e  ldc.i4.1
0xbf8f  add
0xbf90  stloc.1
0xbf91  ldloc.1
0xbf92  ldarg.0
0xbf93  callvirt instance int32 [mscorlib]System.String::get_Length()
0xbf98  blt.s    loc_BF7D
0xbf9a  ldloc.0
0xbf9b  ret
```
