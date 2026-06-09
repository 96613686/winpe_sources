# Microsoft.Crm.Workflow.ConditionHandlerDateTime::CompareDateTime

- ea: `0xb390`
- end: `0xb418`
- name: `Microsoft.Crm.Workflow.ConditionHandlerDateTime::CompareDateTime`
- size: `136`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xab90`
- `0xabc0`
- `0xabf0`
- `0xb360`

## callees

- `0xb340`
- `0xb390`

## pseudocode

```c

```

## disassembly

```asm
0xb390  ldarga.s 1
0xb392  call     instance valuetype [mscorlib]System.DateTimeKind [mscorlib]System.DateTime::get_Kind()
0xb397  ldc.i4.1
0xb398  bne.un.s loc_B3AD
0xb39a  ldarga.s 3
0xb39c  call     instance valuetype [mscorlib]System.DateTimeKind [mscorlib]System.DateTime::get_Kind()
0xb3a1  ldc.i4.1
0xb3a2  beq.s    loc_B3AD
0xb3a4  ldarg.0
0xb3a5  ldarg.1
0xb3a6  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.ConditionHandlerDateTime::GetLocalTime(valuetype [mscorlib]System.DateTime utcTime)
0xb3ab  starg.s  1
0xb3ad  ldarga.s 3
0xb3af  call     instance valuetype [mscorlib]System.DateTimeKind [mscorlib]System.DateTime::get_Kind()
0xb3b4  ldc.i4.1
0xb3b5  bne.un.s loc_B3CA
0xb3b7  ldarga.s 1
0xb3b9  call     instance valuetype [mscorlib]System.DateTimeKind [mscorlib]System.DateTime::get_Kind()
0xb3be  ldc.i4.1
0xb3bf  beq.s    loc_B3CA
0xb3c1  ldarg.0
0xb3c2  ldarg.3
0xb3c3  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.ConditionHandlerDateTime::GetLocalTime(valuetype [mscorlib]System.DateTime utcTime)
0xb3c8  starg.s  3
0xb3ca  ldarga.s 1
0xb3cc  ldarg.3
0xb3cd  call     instance int32 [mscorlib]System.DateTime::CompareTo(valuetype [mscorlib]System.DateTime)
0xb3d2  stloc.0
0xb3d3  ldc.i4.0
0xb3d4  stloc.1
0xb3d5  ldarg.2
0xb3d6  switch   loc_B3F1, loc_B400, loc_B3F8, loc_B410, loc_B408
0xb3ef  br.s     loc_B416
0xb3f1  ldloc.0
0xb3f2  brtrue.s loc_B416
0xb3f4  ldc.i4.1
0xb3f5  stloc.1
0xb3f6  br.s     loc_B416
0xb3f8  ldloc.0
0xb3f9  ldc.i4.0
0xb3fa  ble.s    loc_B416
0xb3fc  ldc.i4.1
0xb3fd  stloc.1
0xb3fe  br.s     loc_B416
0xb400  ldloc.0
0xb401  ldc.i4.0
0xb402  bge.s    loc_B416
0xb404  ldc.i4.1
0xb405  stloc.1
0xb406  br.s     loc_B416
0xb408  ldloc.0
0xb409  ldc.i4.0
0xb40a  blt.s    loc_B416
0xb40c  ldc.i4.1
0xb40d  stloc.1
0xb40e  br.s     loc_B416
0xb410  ldloc.0
0xb411  ldc.i4.0
0xb412  bgt.s    loc_B416
0xb414  ldc.i4.1
0xb415  stloc.1
0xb416  ldloc.1
0xb417  ret
```
