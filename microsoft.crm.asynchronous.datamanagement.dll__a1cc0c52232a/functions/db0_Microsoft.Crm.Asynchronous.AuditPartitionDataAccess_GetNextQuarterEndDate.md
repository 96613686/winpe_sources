# Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::GetNextQuarterEndDate

- ea: `0xdb0`
- end: `0xdec`
- name: `Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::GetNextQuarterEndDate`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x7c0`

## pseudocode

```c

```

## disassembly

```asm
0xdb0  ldarga.s 1
0xdb2  call     instance int32 [mscorlib]System.DateTime::get_Month()
0xdb7  ldc.i4.2
0xdb8  add
0xdb9  ldc.i4.3
0xdba  div
0xdbb  stloc.0
0xdbc  ldc.i4.3
0xdbd  ldloc.0
0xdbe  mul
0xdbf  ldc.i4.2
0xdc0  sub
0xdc1  stloc.1
0xdc2  ldloca.s 2
0xdc4  ldarga.s 1
0xdc6  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xdcb  ldloc.1
0xdcc  ldc.i4.1
0xdcd  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0xdd2  ldloca.s 2
0xdd4  ldc.i4.6
0xdd5  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMonths(int32)
0xdda  stloc.3
0xddb  ldloca.s 3
0xddd  ldc.r8   -3.0
0xde6  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMilliseconds(float64)
0xdeb  ret
```
