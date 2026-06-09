# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::ComputeQueryDateTime

- ea: `0x13530`
- end: `0x13563`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::ComputeQueryDateTime`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x11e40`

## callees

- `0x13390`
- `0x133b0`
- `0x134c0`

## pseudocode

```c

```

## disassembly

```asm
0x13530  ldarg.0
0x13531  ldarga.s 1
0x13533  ldarg.0
0x13534  call     instance int32 Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::get_DaysAfterNoActivity()
0x13539  ldc.i4.7
0x1353a  sub
0x1353b  neg
0x1353c  conv.r8
0x1353d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x13542  stloc.0
0x13543  ldloca.s 0
0x13545  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x1354a  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::set_QueryStartTime(valuetype [mscorlib]System.DateTime value)
0x1354f  ldarg.0
0x13550  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x13555  stloc.0
0x13556  ldloca.s 0
0x13558  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x1355d  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.NoActivityCardConfig::set_QueryEndTime(valuetype [mscorlib]System.DateTime value)
0x13562  ret
```
