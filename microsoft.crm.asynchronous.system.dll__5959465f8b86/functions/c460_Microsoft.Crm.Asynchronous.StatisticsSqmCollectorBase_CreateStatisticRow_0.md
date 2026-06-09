# Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::CreateStatisticRow_0

- ea: `0xc460`
- end: `0xc46e`
- name: `Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::CreateStatisticRow_0`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb750`
- `0xbc60`

## callees

- `0xc470`

## pseudocode

```c

```

## disassembly

```asm
0xc460  ldarg.0
0xc461  ldarg.1
0xc462  ldarg.2
0xc463  ldarg.3
0xc464  ldarg.s  4
0xc466  ldarg.s  5
0xc468  call     instance void Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::InternalCreateStatisticRow(class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService service, int32 statisticType, valuetype [mscorlib]System.DateTime startTime, valuetype [mscorlib]System.DateTime endTime, int32 value)
0xc46d  ret
```
