# Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::CreateStatisticRow

- ea: `0xc440`
- end: `0xc459`
- name: `Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::CreateStatisticRow`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xb370`

## callees

- `0xc470`
- `0xc620`
- `0xc650`

## pseudocode

```c

```

## disassembly

```asm
0xc440  ldarg.0
0xc441  ldarg.1
0xc442  ldarg.2
0xc443  ldarg.0
0xc444  ldarg.3
0xc445  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::FormatHourForStartTime(int32 hour)
0xc44a  ldarg.0
0xc44b  ldarg.3
0xc44c  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::FormatHourForEndTime(int32 hour)
0xc451  ldarg.s  4
0xc453  call     instance void Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::InternalCreateStatisticRow(class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService service, int32 statisticType, valuetype [mscorlib]System.DateTime startTime, valuetype [mscorlib]System.DateTime endTime, int32 value)
0xc458  ret
```
