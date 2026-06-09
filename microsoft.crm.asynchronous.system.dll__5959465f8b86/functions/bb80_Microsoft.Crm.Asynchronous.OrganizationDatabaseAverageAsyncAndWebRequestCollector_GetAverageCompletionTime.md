# Microsoft.Crm.Asynchronous.OrganizationDatabaseAverageAsyncAndWebRequestCollector::GetAverageCompletionTime

- ea: `0xbb80`
- end: `0xbc30`
- name: `Microsoft.Crm.Asynchronous.OrganizationDatabaseAverageAsyncAndWebRequestCollector::GetAverageCompletionTime`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xbb00`

## callees

- `0xbb80`
- `0xc690`

## string_xrefs

- `0xbbb6`: `@StatisticTypeCompletionTimeId`
- `0xbbc8`: `@StatisticTypeCompletedCountId`
- `0xbbee`: `GetAverageCompletionTime`

## pseudocode

```c

```

## disassembly

```asm
0xbb80  ldc.r4   0.0
0xbb85  stloc.0
0xbb86  ldarg.1
0xbb87  ldarg.0
0xbb88  ldfld    string Microsoft.Crm.Asynchronous.OrganizationDatabaseAverageAsyncAndWebRequestCollector::averageCompletionTimeSql
0xbb8d  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xbb92  stloc.1
0xbb93  ldloc.1
0xbb94  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xbb99  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xbb9e  dup
0xbb9f  ldstr    aOrganizationid_2// "@OrganizationId"
0xbba4  ldarg.0
0xbba5  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::get_OrganizationId()
0xbbaa  box      [mscorlib]System.Guid
0xbbaf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xbbb4  pop
0xbbb5  dup
0xbbb6  ldstr    aStatistictypec// "@StatisticTypeCompletionTimeId"
0xbbbb  ldarg.2
0xbbbc  box      [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.OperationalMetricsType
0xbbc1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xbbc6  pop
0xbbc7  dup
0xbbc8  ldstr    aStatistictypec_0// "@StatisticTypeCompletedCountId"
0xbbcd  ldarg.3
0xbbce  box      [Microsoft.Crm.Core]Microsoft.Crm.StatisticsDatabase.OperationalMetricsType
0xbbd3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xbbd8  pop
0xbbd9  ldstr    aHoursback// "@HoursBack"
0xbbde  ldarg.s  4
0xbbe0  box      [mscorlib]System.Int32
0xbbe5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xbbea  pop
0xbbeb  ldloc.1
0xbbec  ldc.i4.s 0x37
0xbbee  ldstr    aGetaveragecomp// "GetAverageCompletionTime"
0xbbf3  ldstr    aDDbsShDccm2110_12// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0xbbf8  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xbbfd  stloc.2
0xbbfe  ldloc.2
0xbbff  brfalse.s loc_BC20
0xbc01  ldloc.2
0xbc02  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xbc07  ldtoken  [mscorlib]System.DBNull
0xbc0c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbc11  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xbc16  brfalse.s loc_BC20
0xbc18  ldloc.2
0xbc19  unbox.any [mscorlib]System.Double
0xbc1e  conv.r4
0xbc1f  stloc.0
0xbc20  ldloc.0
0xbc21  stloc.3
0xbc22  leave.s  loc_BC2E
0xbc24  ldloc.1
0xbc25  brfalse.s loc_BC2D
0xbc27  ldloc.1
0xbc28  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbc2d  endfinally
0xbc2e  ldloc.3
0xbc2f  ret
```
