# Microsoft.Crm.Asynchronous.OrganizationDatabaseCollector::RemoveOldRecords

- ea: `0xb670`
- end: `0xb6b3`
- name: `Microsoft.Crm.Asynchronous.OrganizationDatabaseCollector::RemoveOldRecords`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb570`

## callees

- `0xb670`

## string_xrefs

- `0xb67e`: `exec p_DeleteOldStatistics`
- `0xb68c`: `RemoveOldRecords`

## pseudocode

```c

```

## disassembly

```asm
0xb670  ldarg.1
0xb671  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.StatisticsDatabaseService::CreateConnection()
0xb676  stloc.0
0xb677  ldloc.0
0xb678  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xb67d  ldloc.0
0xb67e  ldstr    aExecPDeleteold// "exec p_DeleteOldStatistics"
0xb683  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xb688  stloc.1
0xb689  ldloc.1
0xb68a  ldc.i4.s 0x58
0xb68c  ldstr    aRemoveoldrecor// "RemoveOldRecords"
0xb691  ldstr    aDDbsShDccm2110_10// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0xb696  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xb69b  pop
0xb69c  leave.s  loc_B6B2
0xb69e  ldloc.1
0xb69f  brfalse.s loc_B6A7
0xb6a1  ldloc.1
0xb6a2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb6a7  endfinally
0xb6a8  ldloc.0
0xb6a9  brfalse.s loc_B6B1
0xb6ab  ldloc.0
0xb6ac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb6b1  endfinally
0xb6b2  ret
```
