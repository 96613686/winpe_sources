# Microsoft.Crm.Asynchronous.OrganizationDatabaseAverageAsyncAndWebRequestCollector::.ctor

- ea: `0xbae0`
- end: `0xbaff`
- name: `Microsoft.Crm.Asynchronous.OrganizationDatabaseAverageAsyncAndWebRequestCollector::.ctor`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1b90`

## callees

- `0xc100`

## string_xrefs

- `0xbae1`: `SELECT CONVERT(FLOAT,SUM (a.Result)) / CONVERT(FLOAT,SUM(b.Result)) \n				 FROM StatisticsData a \n				 INNER JOIN StatisticsData b \n				 ON a.EndTime = b.EndTime \n				 WHERE a.StatisticTypeId=@StatisticTypeCompletionTimeId \n				 AND b.StatisticTypeId=@StatisticTypeCompletedCountId \n				 AND a.OrganizationId=@OrganizationId \n				 AND b.OrganizationId=@OrganizationId \n				 AND a.EndTime > DATEADD(hour,@HoursBack,getUtcDate())`
- `0xbaec`: `RequestCompletionAggregationPeriodHours`

## pseudocode

```c

```

## disassembly

```asm
0xbae0  ldarg.0
0xbae1  ldstr    aSelectConvertF// "SELECT CONVERT(FLOAT,SUM (a.Result)) / "...
0xbae6  stfld    string Microsoft.Crm.Asynchronous.OrganizationDatabaseAverageAsyncAndWebRequestCollector::averageCompletionTimeSql
0xbaeb  ldarg.0
0xbaec  ldstr    aRequestcomplet// "RequestCompletionAggregationPeriodHours"
0xbaf1  stfld    string Microsoft.Crm.Asynchronous.OrganizationDatabaseAverageAsyncAndWebRequestCollector::aggregationHistorySetting
0xbaf6  ldarg.0
0xbaf7  ldc.i4.1
0xbaf8  ldarg.1
0xbaf9  call     instance void Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticQueryType queryType, valuetype [mscorlib]System.Guid organizationId)
0xbafe  ret
```
