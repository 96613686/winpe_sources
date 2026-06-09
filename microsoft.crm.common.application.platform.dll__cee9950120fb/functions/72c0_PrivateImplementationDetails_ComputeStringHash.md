# <PrivateImplementationDetails>::ComputeStringHash

- ea: `0x72c0`
- end: `0x72ec`
- name: `<PrivateImplementationDetails>::ComputeStringHash`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2c70`

## callees

- `0x72c0`

## pseudocode

```c

```

## disassembly

```asm
0x72c0  ldarg.0
0x72c1  brfalse.s loc_72EA
0x72c3  ldc.i4   0x811C9DC5
0x72c8  stloc.0
0x72c9  ldc.i4.0
0x72ca  stloc.1
0x72cb  br.s     loc_72E1
0x72cd  ldarg.0
0x72ce  ldloc.1
0x72cf  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x72d4  ldloc.0
0x72d5  xor
0x72d6  ldc.i4   0x1000193
0x72db  mul
0x72dc  stloc.0
0x72dd  ldloc.1
0x72de  ldc.i4.1
0x72df  add
0x72e0  stloc.1
0x72e1  ldloc.1
0x72e2  ldarg.0
0x72e3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x72e8  blt.s    loc_72CD
0x72ea  ldloc.0
0x72eb  ret
```
