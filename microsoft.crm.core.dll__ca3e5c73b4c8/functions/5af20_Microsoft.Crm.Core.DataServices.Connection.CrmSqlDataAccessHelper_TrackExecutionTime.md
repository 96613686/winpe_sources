# Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::TrackExecutionTime

- ea: `0x5af20`
- end: `0x5b382`
- name: `Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::TrackExecutionTime`
- size: `1122`
- prototype: ``
- caller_count: `4`
- callee_count: `45`
- tags: `service_task, broker_com_uri`

## callers

- `0x4ef30`
- `0x65890`
- `0x65a60`
- `0x65be0`

## callees

- `0x17d70`
- `0x17d90`
- `0x1c0b0`
- `0x1c110`
- `0x1c220`
- `0x1c350`
- `0x1d020`
- `0x1eaa0`
- `0x2db80`
- `0x2dba0`
- `0x33210`
- `0x33240`
- `0x51500`
- `0x51530`
- `0x51560`
- `0x56ad0`
- `0x56bb0`
- `0x56c80`
- `0x59e40`
- `0x5a370`
- `0x5a390`
- `0x5a3b0`
- `0x5a3d0`
- `0x5a3f0`
- `0x5a410`
- `0x5a430`
- `0x5a450`
- `0x5a470`
- `0x5a490`
- `0x5a4b0`
- `0x5a4d0`
- `0x5a4f0`
- `0x5a510`
- `0x5a530`
- `0x5a550`
- `0x5a570`
- `0x5a590`
- `0x5a5b0`
- `0x5a5d0`
- `0x5a5f0`
- `0x5a610`
- `0x5af20`
- `0x5b390`
- `0x5b3f0`
- `0x5b470`

## string_xrefs

- `0x5b33f`: `Query execution time: {0:F1} seconds; database: {1}; command: {2}; CommandTimeout: {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x5af20  ldarg.1
0x5af21  callvirt instance void Microsoft.Crm.TimeTracker::Stop()
0x5af26  call     class Microsoft.Crm.ThreadLogCollector Microsoft.Crm.ThreadSpecificLogger::get_LogData()
0x5af2b  ldarg.1
0x5af2c  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x5af31  stloc.s  4
0x5af33  ldloca.s 4
0x5af35  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x5af3a  callvirt instance void Microsoft.Crm.ThreadLogCollector::AddSqlQueryStatistic(int64 ticks)
0x5af3f  call     class Microsoft.Crm.MetricsReporting Microsoft.Crm.MetricsReporting::get_Instance()
0x5af44  ldstr    aSqlexecutions// "SqlExecutions"
0x5af49  ldarg.1
0x5af4a  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x5af4f  stloc.s  4
0x5af51  ldloca.s 4
0x5af53  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x5af58  conv.r8
0x5af59  ldc.r8   10000.0
0x5af62  div
0x5af63  ldnull
0x5af64  callvirt instance class Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric Microsoft.Crm.MetricsReporting::AddCounterMetric(string name, float64 value, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x5af69  pop
0x5af6a  ldarg.0
0x5af6b  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x5af70  isinst   [System.Data]System.Data.SqlClient.SqlConnection
0x5af75  stloc.0
0x5af76  call     class Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails Microsoft.Crm.Core.DataServices.DataPerformance.CrmDbQueryDetails::get_QueryDetails()
0x5af7b  stloc.1
0x5af7c  ldarg.1
0x5af7d  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x5af82  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::queryExecutionTimeThresholdForDpd
0x5af87  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x5af8c  brfalse  loc_5B21A
0x5af91  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5af96  stloc.s  5
0x5af98  ldstr    a0D41D22D23D24D// "{0:D4}{1:D2}{2:D2}{3:D2}{4:D2}{5:D2}"
0x5af9d  ldc.i4.6
0x5af9e  newarr   [mscorlib]System.Object
0x5afa3  dup
0x5afa4  ldc.i4.0
0x5afa5  ldloca.s 5
0x5afa7  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x5afac  box      [mscorlib]System.Int32
0x5afb1  stelem.ref
0x5afb2  dup
0x5afb3  ldc.i4.1
0x5afb4  ldloca.s 5
0x5afb6  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x5afbb  box      [mscorlib]System.Int32
0x5afc0  stelem.ref
0x5afc1  dup
0x5afc2  ldc.i4.2
0x5afc3  ldloca.s 5
0x5afc5  call     instance int32 [mscorlib]System.DateTime::get_Day()
0x5afca  box      [mscorlib]System.Int32
0x5afcf  stelem.ref
0x5afd0  dup
0x5afd1  ldc.i4.3
0x5afd2  ldloca.s 5
0x5afd4  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x5afd9  box      [mscorlib]System.Int32
0x5afde  stelem.ref
0x5afdf  dup
0x5afe0  ldc.i4.4
0x5afe1  ldloca.s 5
0x5afe3  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0x5afe8  box      [mscorlib]System.Int32
0x5afed  stelem.ref
0x5afee  dup
0x5afef  ldc.i4.5
0x5aff0  ldloca.s 5
0x5aff2  call     instance int32 [mscorlib]System.DateTime::get_Second()
0x5aff7  box      [mscorlib]System.Int32
0x5affc  stelem.ref
0x5affd  call     string [mscorlib]System.String::Format(string, object[])
0x5b002  stloc.s  6
0x5b004  ldstr    a01D7// "{0}_{1:D7}"
0x5b009  ldloc.1
0x5b00a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OrganizationId()
0x5b00f  box      [mscorlib]System.Guid
0x5b014  ldloca.s 5
0x5b016  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x5b01b  ldc.i4   0x989680
0x5b020  conv.i8
0x5b021  rem
0x5b022  box      [mscorlib]System.Int64
0x5b027  call     string [mscorlib]System.String::Format(string, object, object)
0x5b02c  stloc.s  7
0x5b02e  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x5b033  stloc.s  8
0x5b035  ldarg.2
0x5b036  ldstr    a2_0// "-2"
0x5b03b  callvirt instance bool [mscorlib]System.String::Equals(string)
0x5b040  brtrue   loc_5B0F2
0x5b045  ldarg.1
0x5b046  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x5b04b  stloc.s  4
0x5b04d  ldloca.s 4
0x5b04f  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x5b054  ldc.r8   5000.0
0x5b05d  clt.un
0x5b05f  ldc.i4.0
0x5b060  ceq
0x5b062  ldarg.1
0x5b063  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x5b068  stloc.s  4
0x5b06a  ldloca.s 4
0x5b06c  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x5b071  ldc.r8   30000.0
0x5b07a  cgt.un
0x5b07c  ldc.i4.0
0x5b07d  ceq
0x5b07f  and
0x5b080  brfalse.s loc_5B0AD
0x5b082  call     class Microsoft.Crm.MetricsReporting Microsoft.Crm.MetricsReporting::get_Instance()
0x5b087  ldstr    aMediumslowquer// "MediumSlowQueryCount"
0x5b08c  ldarg.1
0x5b08d  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x5b092  stloc.s  4
0x5b094  ldloca.s 4
0x5b096  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x5b09b  conv.r8
0x5b09c  ldc.r8   10000.0
0x5b0a5  div
0x5b0a6  ldnull
0x5b0a7  callvirt instance class Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric Microsoft.Crm.MetricsReporting::AddCounterMetric(string name, float64 value, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x5b0ac  pop
0x5b0ad  ldarg.1
0x5b0ae  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x5b0b3  stloc.s  4
0x5b0b5  ldloca.s 4
0x5b0b7  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x5b0bc  ldc.r8   30000.0
0x5b0c5  ble.un.s loc_5B0F2
0x5b0c7  call     class Microsoft.Crm.MetricsReporting Microsoft.Crm.MetricsReporting::get_Instance()
0x5b0cc  ldstr    aLongrunningque// "LongRunningQueryCount"
0x5b0d1  ldarg.1
0x5b0d2  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x5b0d7  stloc.s  4
0x5b0d9  ldloca.s 4
0x5b0db  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x5b0e0  conv.r8
0x5b0e1  ldc.r8   10000.0
0x5b0ea  div
0x5b0eb  ldnull
0x5b0ec  callvirt instance class Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric Microsoft.Crm.MetricsReporting::AddCounterMetric(string name, float64 value, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x5b0f1  pop
0x5b0f2  call     class Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource::get_Instance()
0x5b0f7  ldloc.1
0x5b0f8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OrganizationId()
0x5b0fd  ldarg.0
0x5b0fe  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x5b103  dup
0x5b104  brtrue.s loc_5B10A
0x5b106  pop
0x5b107  ldnull
0x5b108  br.s     loc_5B10F
0x5b10a  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0x5b10f  call     string Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x5b114  call     string Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x5b119  ldarg.1
0x5b11a  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x5b11f  stloc.s  4
0x5b121  ldloca.s 4
0x5b123  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x5b128  ldarg.0
0x5b129  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x5b12e  ldloc.1
0x5b12f  callvirt instance valuetype Microsoft.Crm.Core.DataServices.DataPerformance.InitiatorType Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_Initiator()
0x5b134  stloc.s  9
0x5b136  ldloca.s 9
0x5b138  constrained. Microsoft.Crm.Core.DataServices.DataPerformance.InitiatorType
0x5b13e  callvirt instance string [mscorlib]System.Object::ToString()
0x5b143  ldloc.1
0x5b144  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_ComponentName()
0x5b149  ldloc.1
0x5b14a  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_SolutionName()
0x5b14f  ldloc.1
0x5b150  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_EntityName()
0x5b155  ldloc.1
0x5b156  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OperationName()
0x5b15b  ldloc.s  6
0x5b15d  ldloc.s  7
0x5b15f  call     string Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserId()
0x5b164  ldloc.1
0x5b165  callvirt instance bool Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_IsLeadingWildCardQuery()
0x5b16a  ldarg.2
0x5b16b  ldloc.0
0x5b16c  brfalse.s loc_5B176
0x5b16e  ldloc.0
0x5b16f  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.SqlClient.SqlConnection::get_ClientConnectionId()
0x5b174  br.s     loc_5B17B
0x5b176  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5b17b  ldarg.0
0x5b17c  callvirt instance int32 [System.Data]System.Data.IDbCommand::get_CommandTimeout()
0x5b181  call     string Microsoft.Crm.MetricsReporting::get_CurrentRequestId()
0x5b186  ldloc.s  8
0x5b188  callvirt instance void Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource::DBSlowQueryDiagnostics(valuetype [mscorlib]System.Guid organizationId, string orgDbName, string userPuid, string applicationVersion, float64 executionTimeInMilliseconds, string sqlText, string initiator, string componentName, string solutionName, string entityName, string operationName, string recordPartitionKey, string recordRowKey, string userId, bool isLeadingWildCardQuickFind, string errorCode, valuetype [mscorlib]System.Guid clientConnectionId, int32 commandTimeout, string reqId, valuetype [mscorlib]System.Guid executionId)
0x5b18d  call     class Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource::get_Instance()
0x5b192  ldloc.1
0x5b193  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OrganizationId()
0x5b198  ldarg.0
0x5b199  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x5b19e  dup
0x5b19f  brtrue.s loc_5B1A5
0x5b1a1  pop
0x5b1a2  ldnull
0x5b1a3  br.s     loc_5B1AA
0x5b1a5  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0x5b1aa  ldloc.1
0x5b1ab  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_SecurityOption()
0x5b1b0  ldloc.1
0x5b1b1  callvirt instance int64 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_RecordCount()
0x5b1b6  ldloc.1
0x5b1b7  callvirt instance int32 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OwnerPrincipalsCount()
0x5b1bc  ldloc.1
0x5b1bd  callvirt instance int32 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_BusinessUnitReadPrivilegeLength()
0x5b1c2  ldloc.1
0x5b1c3  callvirt instance int32 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_BusinessUnitCount()
0x5b1c8  ldloc.1
0x5b1c9  callvirt instance int64 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_POAChildUsersCount()
0x5b1ce  ldloc.1
0x5b1cf  callvirt instance int64 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_POATeamPrincipalsCount()
0x5b1d4  ldloc.1
0x5b1d5  callvirt instance int64 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_POAShareCount()
0x5b1da  call     string [mscorlib]System.Environment::get_StackTrace()
0x5b1df  ldloc.1
0x5b1e0  callvirt instance int32 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_POAShareCountPercentOfTotalRows()
0x5b1e5  ldloc.1
0x5b1e6  callvirt instance int64 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_POARecordCountForOwnerID()
0x5b1eb  ldloc.1
0x5b1ec  callvirt instance int32 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_POARecordCountForOwnerIDPercentOfTotalRows()
0x5b1f1  ldloc.1
0x5b1f2  callvirt instance int64 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_POARecordCountForOwningBU()
0x5b1f7  ldloc.1
0x5b1f8  callvirt instance int32 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_POARecordCountForOwningBUPercentOfTotalRows()
0x5b1fd  ldloc.1
0x5b1fe  callvirt instance int32 Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_ObjectTypeCode()
0x5b203  ldloc.1
0x5b204  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_PrincipalID()
0x5b209  call     string Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x5b20e  call     string Microsoft.Crm.MetricsReporting::get_CurrentRequestId()
0x5b213  ldloc.s  8
0x5b215  callvirt instance void Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource::DBSlowQueryDiagnosticsExtended(valuetype [mscorlib]System.Guid organizationId, string orgDbName, string securityOption, int64 recordCount, int32 ownerPrincipalsCount, int32 businessUnitReadPrivilegeLength, int32 businessUnitCount, int64 poaChildUsersCount, int64 poaTeamPrincipalsCount, int64 poaShareCount, string environmentStackTrace, int32 poaShareCountPercentOfTotalRows, int64 poaRecordCountForOwnerID, int32 poaRecordCountForOwnerIDPercentOfTotalRows, int64 poaRecordCountForOwningBU, int32 poaRecordCountForOwningBUPercentOfTotalRows, int32 objectTypeCode, valuetype [mscorlib]System.Guid principalId, string applicationVersion, string reqId, valuetype [mscorlib]System.Guid executionId)
0x5b21a  ldarg.1
0x5b21b  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x5b220  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::queryExecutionTimeThreshold
0x5b225  call     bool [mscorlib]System.TimeSpan::op_LessThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x5b22a  brfalse.s loc_5B22D
0x5b22c  ret
0x5b22d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5b232  ldstr    a0Server1// "{0}; Server:{1}"
0x5b237  ldc.i4.2
0x5b238  newarr   [mscorlib]System.Object
0x5b23d  dup
0x5b23e  ldc.i4.0
0x5b23f  ldloc.0
0x5b240  brtrue.s loc_5B245
0x5b242  ldnull
0x5b243  br.s     loc_5B24B
0x5b245  ldloc.0
0x5b246  callvirt instance string [System.Data]System.Data.Common.DbConnection::get_Database()
0x5b24b  stelem.ref
0x5b24c  dup
0x5b24d  ldc.i4.1
0x5b24e  ldloc.0
0x5b24f  brtrue.s loc_5B254
0x5b251  ldnull
0x5b252  br.s     loc_5B25A
0x5b254  ldloc.0
0x5b255  callvirt instance string [System.Data]System.Data.Common.DbConnection::get_DataSource()
0x5b25a  stelem.ref
0x5b25b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5b260  stloc.2
0x5b261  call     bool Microsoft.Crm.SQLLogger::get_IsEnabled()
0x5b266  brfalse.s loc_5B2A0
0x5b268  ldloc.2
0x5b269  ldarg.1
0x5b26a  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.TimeTracker::get_Elapsed()
0x5b26f  stloc.s  4
0x5b271  ldloca.s 4
0x5b273  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x5b278  ldarg.0
0x5b279  ldloca.s 0xA
0x5b27b  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x5b281  ldloc.s  0xA
0x5b283  ldc.i4.1
0x5b284  call     string Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::GetTraceMessage(class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Nullable`1<int32> truncateToLength, bool includeSQLParameterData)
0x5b289  ldarg.0
0x5b28a  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x5b28f  dup
0x5b290  brtrue.s loc_5B296
0x5b292  pop
0x5b293  ldnull
0x5b294  br.s     loc_5B29B
0x5b296  callvirt instance string [System.Data]System.Data.IDbConnection::get_ConnectionString()
0x5b29b  call     void Microsoft.Crm.SQLLogger::Log(string databaseLog, float64 elapsedSeconds, string traceMessage, string connectionString)
0x5b2a0  ldc.i4.2
0x5b2a1  stloc.3
0x5b2a2  newobj   instance void Microsoft.Crm.CrmEventLog::.ctor()
  ... truncated ...
```
