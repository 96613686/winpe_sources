# Microsoft.Crm.Asynchronous.OrganizationDatabaseIOCollector::RemoveOldRecords

- ea: `0xb9f0`
- end: `0xba36`
- name: `Microsoft.Crm.Asynchronous.OrganizationDatabaseIOCollector::RemoveOldRecords`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb6e0`

## callees

- `0xb9f0`

## string_xrefs

- `0xb9fe`: `exec p_DeleteOldStatistics`
- `0xba0f`: `RemoveOldRecords`

## pseudocode

```c

```

## disassembly

```asm
0xb9f0  ldarg.1
0xb9f1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsDatabaseService::CreateConnection()
0xb9f6  stloc.0
0xb9f7  ldloc.0
0xb9f8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xb9fd  ldloc.0
0xb9fe  ldstr    aExecPDeleteold// "exec p_DeleteOldStatistics"
0xba03  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xba08  stloc.1
0xba09  ldloc.1
0xba0a  ldc.i4   0xC3
0xba0f  ldstr    aRemoveoldrecor// "RemoveOldRecords"
0xba14  ldstr    aDDbsShDccm2110_11// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0xba19  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xba1e  pop
0xba1f  leave.s  loc_BA35
0xba21  ldloc.1
0xba22  brfalse.s loc_BA2A
0xba24  ldloc.1
0xba25  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xba2a  endfinally
0xba2b  ldloc.0
0xba2c  brfalse.s loc_BA34
0xba2e  ldloc.0
0xba2f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xba34  endfinally
0xba35  ret
```
