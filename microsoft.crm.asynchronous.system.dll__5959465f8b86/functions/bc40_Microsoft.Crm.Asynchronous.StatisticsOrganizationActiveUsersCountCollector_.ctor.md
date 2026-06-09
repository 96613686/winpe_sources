# Microsoft.Crm.Asynchronous.StatisticsOrganizationActiveUsersCountCollector::.ctor

- ea: `0xbc40`
- end: `0xbc5f`
- name: `Microsoft.Crm.Asynchronous.StatisticsOrganizationActiveUsersCountCollector::.ctor`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1bf0`

## callees

- `0xc100`

## string_xrefs

- `0xbc41`: `SELECT COUNT(CrmUserId) \n					 FROM SystemUserOrganizations \n					 WHERE OrganizationId = @OrganizationId \n					AND LastAccessTime >  DATEADD(minute,@MinutesInterval,getUtcDate()) `

## pseudocode

```c

```

## disassembly

```asm
0xbc40  ldarg.0
0xbc41  ldstr    aSelectCountCrm// "SELECT COUNT(CrmUserId) \r\n\t\t\t\t\t "...
0xbc46  stfld    string Microsoft.Crm.Asynchronous.StatisticsOrganizationActiveUsersCountCollector::activeUsersCountSql
0xbc4b  ldarg.0
0xbc4c  ldstr    aActiveusertime// "ActiveUserTimeWindowMinutes"
0xbc51  stfld    string Microsoft.Crm.Asynchronous.StatisticsOrganizationActiveUsersCountCollector::activeUserTimeWindow
0xbc56  ldarg.0
0xbc57  ldc.i4.1
0xbc58  ldarg.1
0xbc59  call     instance void Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticQueryType queryType, valuetype [mscorlib]System.Guid organizationId)
0xbc5e  ret
```
