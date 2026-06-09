# Microsoft.Crm.Transformations.Concatenate::Evaluate

- ea: `0xa0`
- end: `0x1f8`
- name: `Microsoft.Crm.Transformations.Concatenate::Evaluate`
- size: `344`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xa0`

## pseudocode

```c

```

## disassembly

```asm
0xa0  ldarg.1
0xa1  brfalse.s loc_A9
0xa3  ldarg.1
0xa4  ldlen
0xa5  conv.i4
0xa6  ldc.i4.4
0xa7  beq.s    loc_BA
0xa9  ldc.i4   0x80048506
0xae  ldc.i4.0
0xaf  newarr   [mscorlib]System.Object
0xb4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xb9  throw
0xba  ldarg.1
0xbb  ldc.i4.0
0xbc  ldelem.ref
0xbd  isinst   [mscorlib]System.String
0xc2  stloc.0
0xc3  ldarg.1
0xc4  ldc.i4.1
0xc5  ldelem.ref
0xc6  isinst   [mscorlib]System.String
0xcb  stloc.1
0xcc  ldarg.1
0xcd  ldc.i4.2
0xce  ldelem.ref
0xcf  brfalse.s loc_102
0xd1  ldarg.1
0xd2  ldc.i4.2
0xd3  ldelem.ref
0xd4  isinst   [mscorlib]System.String
0xd9  brtrue.s loc_102
0xdb  ldc.i4   0x80048507
0xe0  ldc.i4.3
0xe1  newarr   [mscorlib]System.Object
0xe6  dup
0xe7  ldc.i4.0
0xe8  ldstr    a3// "3"
0xed  stelem.ref
0xee  dup
0xef  ldc.i4.1
0xf0  ldarg.1
0xf1  ldc.i4.2
0xf2  ldelem.ref
0xf3  stelem.ref
0xf4  dup
0xf5  ldc.i4.2
0xf6  ldstr    aString// "String"
0xfb  stelem.ref
0xfc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x101  throw
0x102  ldarg.1
0x103  ldc.i4.2
0x104  ldelem.ref
0x105  isinst   [mscorlib]System.String
0x10a  stloc.2
0x10b  ldarg.1
0x10c  ldc.i4.3
0x10d  ldelem.ref
0x10e  isinst   object[]
0x113  stloc.3
0x114  ldloc.3
0x115  brtrue.s loc_13E
0x117  ldc.i4   0x80048507
0x11c  ldc.i4.3
0x11d  newarr   [mscorlib]System.Object
0x122  dup
0x123  ldc.i4.0
0x124  ldstr    a4// "4"
0x129  stelem.ref
0x12a  dup
0x12b  ldc.i4.1
0x12c  ldarg.1
0x12d  ldc.i4.3
0x12e  ldelem.ref
0x12f  stelem.ref
0x130  dup
0x131  ldc.i4.2
0x132  ldstr    aString_0// "String[]"
0x137  stelem.ref
0x138  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x13d  throw
0x13e  ldloc.3
0x13f  ldlen
0x140  brtrue.s loc_166
0x142  ldc.i4   0x80048511
0x147  ldc.i4.2
0x148  newarr   [mscorlib]System.Object
0x14d  dup
0x14e  ldc.i4.0
0x14f  ldstr    a4// "4"
0x154  stelem.ref
0x155  dup
0x156  ldc.i4.1
0x157  ldloc.3
0x158  ldlen
0x159  conv.i4
0x15a  box      [mscorlib]System.Int32
0x15f  stelem.ref
0x160  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x165  throw
0x166  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x16b  stloc.s  4
0x16d  ldloc.0
0x16e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x173  brtrue.s loc_17E
0x175  ldloc.s  4
0x177  ldloc.0
0x178  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x17d  pop
0x17e  ldc.i4.0
0x17f  stloc.s  5
0x181  ldc.i4.0
0x182  stloc.s  6
0x184  br.s     loc_1BC
0x186  ldloc.3
0x187  ldloc.s  6
0x189  ldelem.ref
0x18a  castclass [mscorlib]System.String
0x18f  stloc.s  7
0x191  ldloc.s  7
0x193  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x198  brtrue.s loc_1B6
0x19a  ldloc.s  5
0x19c  brtrue.s loc_1A3
0x19e  ldc.i4.1
0x19f  stloc.s  5
0x1a1  br.s     loc_1AC
0x1a3  ldloc.s  4
0x1a5  ldloc.2
0x1a6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1ab  pop
0x1ac  ldloc.s  4
0x1ae  ldloc.s  7
0x1b0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1b5  pop
0x1b6  ldloc.s  6
0x1b8  ldc.i4.1
0x1b9  add
0x1ba  stloc.s  6
0x1bc  ldloc.s  6
0x1be  ldloc.3
0x1bf  ldlen
0x1c0  conv.i4
0x1c1  blt.s    loc_186
0x1c3  ldloc.s  5
0x1c5  brtrue.s loc_1D6
0x1c7  ldc.i4.1
0x1c8  newarr   [mscorlib]System.Object
0x1cd  dup
0x1ce  ldc.i4.0
0x1cf  ldsfld   string [mscorlib]System.String::Empty
0x1d4  stelem.ref
0x1d5  ret
0x1d6  ldloc.1
0x1d7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1dc  brtrue.s loc_1E7
0x1de  ldloc.s  4
0x1e0  ldloc.1
0x1e1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1e6  pop
0x1e7  ldc.i4.1
0x1e8  newarr   [mscorlib]System.Object
0x1ed  dup
0x1ee  ldc.i4.0
0x1ef  ldloc.s  4
0x1f1  callvirt instance string [mscorlib]System.Object::ToString()
0x1f6  stelem.ref
0x1f7  ret
```
