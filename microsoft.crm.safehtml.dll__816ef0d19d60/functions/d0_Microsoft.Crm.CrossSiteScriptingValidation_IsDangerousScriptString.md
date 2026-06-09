# Microsoft.Crm.CrossSiteScriptingValidation::IsDangerousScriptString

- ea: `0xd0`
- end: `0x193`
- name: `Microsoft.Crm.CrossSiteScriptingValidation::IsDangerousScriptString`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1e0`

## callees

- `0xd0`

## pseudocode

```c

```

## disassembly

```asm
0xd0  ldarg.0
0xd1  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd6  stloc.0
0xd7  ldarg.1
0xd8  ldc.i4.6
0xd9  add
0xda  ldloc.0
0xdb  blt.s    loc_DF
0xdd  ldc.i4.0
0xde  ret
0xdf  ldarg.0
0xe0  ldarg.1
0xe1  ldc.i4.1
0xe2  add
0xe3  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xe8  ldc.i4.s 0x63
0xea  beq.s    loc_F9
0xec  ldarg.0
0xed  ldarg.1
0xee  ldc.i4.1
0xef  add
0xf0  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xf5  ldc.i4.s 0x43
0xf7  bne.un.s loc_161
0xf9  ldarg.0
0xfa  ldarg.1
0xfb  ldc.i4.2
0xfc  add
0xfd  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x102  ldc.i4.s 0x72
0x104  beq.s    loc_113
0x106  ldarg.0
0x107  ldarg.1
0x108  ldc.i4.2
0x109  add
0x10a  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x10f  ldc.i4.s 0x52
0x111  bne.un.s loc_161
0x113  ldarg.0
0x114  ldarg.1
0x115  ldc.i4.3
0x116  add
0x117  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x11c  ldc.i4.s 0x69
0x11e  beq.s    loc_12D
0x120  ldarg.0
0x121  ldarg.1
0x122  ldc.i4.3
0x123  add
0x124  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x129  ldc.i4.s 0x49
0x12b  bne.un.s loc_161
0x12d  ldarg.0
0x12e  ldarg.1
0x12f  ldc.i4.4
0x130  add
0x131  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x136  ldc.i4.s 0x70
0x138  beq.s    loc_147
0x13a  ldarg.0
0x13b  ldarg.1
0x13c  ldc.i4.4
0x13d  add
0x13e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x143  ldc.i4.s 0x50
0x145  bne.un.s loc_161
0x147  ldarg.0
0x148  ldarg.1
0x149  ldc.i4.5
0x14a  add
0x14b  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x150  ldc.i4.s 0x74
0x152  beq.s    loc_163
0x154  ldarg.0
0x155  ldarg.1
0x156  ldc.i4.5
0x157  add
0x158  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x15d  ldc.i4.s 0x54
0x15f  beq.s    loc_163
0x161  ldc.i4.0
0x162  ret
0x163  ldarg.1
0x164  ldc.i4.6
0x165  add
0x166  starg.s  1
0x168  br.s     loc_16F
0x16a  ldarg.1
0x16b  ldc.i4.1
0x16c  add
0x16d  starg.s  1
0x16f  ldarg.1
0x170  ldloc.0
0x171  bge.s    loc_181
0x173  ldarg.0
0x174  ldarg.1
0x175  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x17a  call     bool [mscorlib]System.Char::IsWhiteSpace(char)
0x17f  brtrue.s loc_16A
0x181  ldarg.1
0x182  ldloc.0
0x183  bge.s    loc_191
0x185  ldarg.0
0x186  ldarg.1
0x187  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x18c  ldc.i4.s 0x3A
0x18e  ceq
0x190  ret
0x191  ldc.i4.0
0x192  ret
```
