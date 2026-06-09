# Microsoft.Crm.Asynchronous.SqlUnparameterizer::ReplaceParameters

- ea: `0x6580`
- end: `0x6648`
- name: `Microsoft.Crm.Asynchronous.SqlUnparameterizer::ReplaceParameters`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x63d0`

## callees

- `0x6500`
- `0x6580`

## pseudocode

```c

```

## disassembly

```asm
0x6580  br       loc_663B
0x6585  ldarg.0
0x6586  ldc.i4.s 0x3D
0x6588  ldarg.2
0x6589  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x658e  stloc.0
0x658f  ldarg.0
0x6590  ldarg.2
0x6591  ldloc.0
0x6592  ldarg.2
0x6593  sub
0x6594  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x6599  stloc.1
0x659a  ldloc.1
0x659b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x65a0  brtrue.s loc_65A4
0x65a2  ldc.i4.0
0x65a3  ret
0x65a4  ldloc.0
0x65a5  ldc.i4.1
0x65a6  add
0x65a7  starg.s  2
0x65a9  ldarg.2
0x65aa  stloc.0
0x65ab  ldarg.0
0x65ac  ldloc.0
0x65ad  ldarg.3
0x65ae  ldloca.s 0
0x65b0  call     bool Microsoft.Crm.Asynchronous.SqlUnparameterizer::GetParameterValue(string sql, int32 start, int32 end, [out] int32& newStart)
0x65b5  brtrue.s loc_65B9
0x65b7  ldc.i4.0
0x65b8  ret
0x65b9  ldarg.0
0x65ba  ldarg.2
0x65bb  ldloc.0
0x65bc  ldarg.2
0x65bd  sub
0x65be  ldc.i4.1
0x65bf  add
0x65c0  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x65c5  stloc.2
0x65c6  ldloc.0
0x65c7  ldarg.3
0x65c8  beq.s    loc_65CE
0x65ca  ldloc.0
0x65cb  ldc.i4.2
0x65cc  add
0x65cd  stloc.0
0x65ce  ldloc.2
0x65cf  callvirt instance int32 [mscorlib]System.String::get_Length()
0x65d4  brtrue.s loc_65D8
0x65d6  ldc.i4.0
0x65d7  ret
0x65d8  ldloc.2
0x65d9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x65de  ldc.i4.2
0x65df  blt.s    loc_662D
0x65e1  ldloc.2
0x65e2  ldc.i4.0
0x65e3  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x65e8  ldc.i4.s 0x27
0x65ea  bne.un.s loc_662D
0x65ec  ldloc.2
0x65ed  ldc.i4.1
0x65ee  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x65f3  ldc.i4.s 0x27
0x65f5  bne.un.s loc_662D
0x65f7  ldloc.2
0x65f8  ldloc.2
0x65f9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x65fe  ldc.i4.1
0x65ff  sub
0x6600  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x6605  ldc.i4.s 0x27
0x6607  bne.un.s loc_661B
0x6609  ldloc.2
0x660a  ldloc.2
0x660b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6610  ldc.i4.2
0x6611  sub
0x6612  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x6617  ldc.i4.s 0x27
0x6619  beq.s    loc_661D
0x661b  ldc.i4.0
0x661c  ret
0x661d  ldloc.2
0x661e  ldc.i4.1
0x661f  ldloc.2
0x6620  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6625  ldc.i4.2
0x6626  sub
0x6627  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x662c  stloc.2
0x662d  ldloc.0
0x662e  starg.s  2
0x6630  ldarg.1
0x6631  ldarg.1
0x6632  ldind.ref
0x6633  ldloc.1
0x6634  ldloc.2
0x6635  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x663a  stind.ref
0x663b  ldc.i4.m1
0x663c  ldarg.2
0x663d  beq.s    loc_6646
0x663f  ldarg.2
0x6640  ldarg.3
0x6641  blt      loc_6585
0x6646  ldc.i4.1
0x6647  ret
```
