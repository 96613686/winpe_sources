# Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::CreateScalarStatisticRow

- ea: `0xc3e0`
- end: `0xc435`
- name: `Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::CreateScalarStatisticRow`
- size: `85`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb570`
- `0xb750`
- `0xb810`
- `0xbfe0`
- `0xc890`

## callees

- `0xc470`

## pseudocode

```c

```

## disassembly

```asm
0xc3e0  ldloca.s 0
0xc3e2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xc3e7  stloc.1
0xc3e8  ldloca.s 1
0xc3ea  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xc3ef  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xc3f4  stloc.1
0xc3f5  ldloca.s 1
0xc3f7  call     instance int32 [mscorlib]System.DateTime::get_Month()
0xc3fc  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xc401  stloc.1
0xc402  ldloca.s 1
0xc404  call     instance int32 [mscorlib]System.DateTime::get_Day()
0xc409  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xc40e  stloc.1
0xc40f  ldloca.s 1
0xc411  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0xc416  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xc41b  stloc.1
0xc41c  ldloca.s 1
0xc41e  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0xc423  ldc.i4.0
0xc424  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32)
0xc429  ldarg.0
0xc42a  ldarg.1
0xc42b  ldarg.2
0xc42c  ldloc.0
0xc42d  ldloc.0
0xc42e  ldarg.3
0xc42f  call     instance void Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::InternalCreateStatisticRow(class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService service, int32 statisticType, valuetype [mscorlib]System.DateTime startTime, valuetype [mscorlib]System.DateTime endTime, int32 value)
0xc434  ret
```
