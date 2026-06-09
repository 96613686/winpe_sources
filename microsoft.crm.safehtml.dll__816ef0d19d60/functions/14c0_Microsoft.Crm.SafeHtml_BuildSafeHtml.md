# Microsoft.Crm.SafeHtml::BuildSafeHtml

- ea: `0x14c0`
- end: `0x155d`
- name: `Microsoft.Crm.SafeHtml::BuildSafeHtml`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14a0`

## callees

- `0x14c0`
- `0x1ae0`
- `0x1af0`

## pseudocode

```c

```

## disassembly

```asm
0x14c0  ldc.i4.0
0x14c1  conv.u
0x14c2  stloc.0
0x14c3  ldarg.2
0x14c4  ldsfld   string [mscorlib]System.String::Empty
0x14c9  stind.ref
0x14ca  ldarg.0
0x14cb  brfalse.s loc_14D5
0x14cd  ldarg.0
0x14ce  callvirt instance int32 [mscorlib]System.String::get_Length()
0x14d3  brtrue.s loc_14D7
0x14d5  ldc.i4.0
0x14d6  ret
0x14d7  nop
0x14d8  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x14dd  ldarg.0
0x14de  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x14e3  dup
0x14e4  ldlen
0x14e5  conv.i4
0x14e6  stloc.1
0x14e7  ldc.i4.0
0x14e8  stloc.2
0x14e9  ldloc.1
0x14ea  ldc.i4   0xFDE9
0x14ef  ldloca.s 0
0x14f1  conv.u
0x14f2  ldloca.s 2
0x14f4  ldc.i4   0x4B0
0x14f9  ldarg.1
0x14fa  ldc.i4   0x2000
0x14ff  or
0x1500  ldc.i4   0x1000
0x1505  or
0x1506  ldc.i4   0x200
0x150b  or
0x150c  call     unsigned int32 NativeMethods::OshFGetSafeHTMLAllocForManaged2(unsigned int8[] rgbSrc, int32 cbSrc, int32 cpSrc, unsigned int8** rgbDst, [out] int32& cbDst, int32 cpDst, int32 grfosh)
0x1511  stloc.3
0x1512  ldloc.2
0x1513  ldc.i4.2
0x1514  div
0x1515  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x151a  stloc.s  4
0x151c  ldc.i4.0
0x151d  stloc.s  5
0x151f  br.s     loc_1538
0x1521  ldloc.0
0x1522  ldloc.s  5
0x1524  add
0x1525  ldind.u2
0x1526  stloc.s  6
0x1528  ldloc.s  4
0x152a  ldloc.s  6
0x152c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1531  pop
0x1532  ldloc.s  5
0x1534  ldc.i4.2
0x1535  add
0x1536  stloc.s  5
0x1538  ldloc.s  5
0x153a  ldloc.2
0x153b  blt.s    loc_1521
0x153d  ldarg.2
0x153e  ldloc.s  4
0x1540  callvirt instance string [mscorlib]System.Object::ToString()
0x1545  stind.ref
0x1546  ldloc.3
0x1547  ldc.i4.1
0x1548  ceq
0x154a  stloc.s  7
0x154c  leave.s  loc_155A
0x154e  ldloc.0
0x154f  ldc.i4.0
0x1550  conv.u
0x1551  beq.s    loc_1559
0x1553  ldloc.0
0x1554  call     void NativeMethods::OshFreePv(void* pv)
0x1559  endfinally
0x155a  ldloc.s  7
0x155c  ret
```
