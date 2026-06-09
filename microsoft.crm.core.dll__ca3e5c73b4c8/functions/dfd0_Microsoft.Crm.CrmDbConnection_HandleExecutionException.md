# Microsoft.Crm.CrmDbConnection::HandleExecutionException

- ea: `0xdfd0`
- end: `0xe317`
- name: `Microsoft.Crm.CrmDbConnection::HandleExecutionException`
- size: `839`
- prototype: ``
- caller_count: `3`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0xdd90`
- `0xe320`
- `0xe350`

## callees

- `0xdd90`
- `0xdfd0`
- `0xe3b0`
- `0xe3d0`
- `0xffb0`
- `0x1c220`
- `0x1c350`
- `0x1d020`
- `0x1eaa0`
- `0x1f510`
- `0x51500`
- `0x51530`
- `0x54770`
- `0x54a10`
- `0x54a60`
- `0x55cd0`
- `0x55d00`
- `0x55d20`
- `0x56ad0`
- `0x56ae0`
- `0x570f0`
- `0x59e40`
- `0x5a390`
- `0x5a3f0`
- `0x5a410`
- `0x5b920`
- `0x5b930`
- `0x5b940`

## string_xrefs

- `0xe10c`: `ConnectionOpened`
- `0xe097`: `Re-opening connection: Exception: {0}`
- `0xe0fd`: `Open the Connection (Retry)`
- `0xe191`: `Retrying SQL command. Connection State: {0}, Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xdfd0  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor()
0xdfd5  callvirt instance class [mscorlib]System.Diagnostics.StackFrame[] [mscorlib]System.Diagnostics.StackTrace::GetFrames()
0xdfda  stloc.s  4
0xdfdc  ldc.i4.0
0xdfdd  stloc.s  5
0xdfdf  br.s     loc_E017
0xdfe1  ldloc.s  4
0xdfe3  ldloc.s  5
0xdfe5  ldelem.ref
0xdfe6  callvirt instance class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Diagnostics.StackFrame::GetMethod()
0xdfeb  stloc.s  6
0xdfed  ldloc.s  6
0xdfef  ldnull
0xdff0  call     bool [mscorlib]System.Reflection.MethodBase::op_Inequality(class [mscorlib]System.Reflection.MethodBase, class [mscorlib]System.Reflection.MethodBase)
0xdff5  brfalse.s loc_E011
0xdff7  ldloc.s  6
0xdff9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0xdffe  ldtoken  Microsoft.Crm.CrmTrace
0xe003  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe008  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xe00d  brfalse.s loc_E011
0xe00f  ldc.i4.0
0xe010  ret
0xe011  ldloc.s  5
0xe013  ldc.i4.1
0xe014  add
0xe015  stloc.s  5
0xe017  ldloc.s  5
0xe019  ldloc.s  4
0xe01b  ldlen
0xe01c  conv.i4
0xe01d  blt.s    loc_DFE1
0xe01f  newobj   instance void Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0xe024  stloc.0
0xe025  ldarg.0
0xe026  isinst   [System.Data]System.Data.SqlClient.SqlException
0xe02b  stloc.1
0xe02c  ldarg.2
0xe02d  isinst   [System.Data]System.Data.SqlClient.SqlConnection
0xe032  stloc.2
0xe033  call     class Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails Microsoft.Crm.Core.DataServices.DataPerformance.CrmDbQueryDetails::get_QueryDetails()
0xe038  stloc.3
0xe039  ldarg.3
0xe03a  brtrue   loc_E217
0xe03f  ldarg.s  6
0xe041  ldind.i4
0xe042  call     class Microsoft.Crm.Core.DataServices.Connection.IConnectionRetryPolicy Microsoft.Crm.CrmDbConnection::get_RetryPolicy()
0xe047  ldarg.0
0xe048  callvirt instance int32 Microsoft.Crm.Core.DataServices.Connection.IConnectionRetryPolicy::RetryCount(class [mscorlib]System.Exception ex)
0xe04d  bge      loc_E217
0xe052  ldarg.2
0xe053  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.IDbConnection::get_State()
0xe058  brtrue   loc_E142
0xe05d  ldarg.s  4
0xe05f  brtrue   loc_E142
0xe064  call     class Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource::get_Instance()
0xe069  ldloc.3
0xe06a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OrganizationId()
0xe06f  call     string Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0xe074  call     string Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0xe079  ldloc.1
0xe07a  brfalse.s loc_E092
0xe07c  ldloc.1
0xe07d  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0xe082  stloc.s  5
0xe084  ldloca.s 5
0xe086  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe08b  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xe090  br.s     loc_E097
0xe092  ldsfld   string [mscorlib]System.String::Empty
0xe097  ldstr    aReOpeningConne// "Re-opening connection: Exception: {0}"
0xe09c  ldarg.0
0xe09d  call     string [mscorlib]System.String::Format(string, object)
0xe0a2  ldarg.1
0xe0a3  ldloc.1
0xe0a4  brfalse.s loc_E0AE
0xe0a6  ldloc.1
0xe0a7  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.SqlClient.SqlException::get_ClientConnectionId()
0xe0ac  br.s     loc_E0BE
0xe0ae  ldloc.2
0xe0af  brfalse.s loc_E0B9
0xe0b1  ldloc.2
0xe0b2  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.SqlClient.SqlConnection::get_ClientConnectionId()
0xe0b7  br.s     loc_E0BE
0xe0b9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe0be  ldarg.s  5
0xe0c0  call     string [mscorlib]System.Environment::get_StackTrace()
0xe0c5  ldloc.3
0xe0c6  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_EntityName()
0xe0cb  ldloc.3
0xe0cc  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OperationName()
0xe0d1  ldarg.2
0xe0d2  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0xe0d7  call     string Microsoft.Crm.MetricsReporting::get_CurrentRequestId()
0xe0dc  callvirt instance void Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource::DBExceptionDiagnostics(valuetype [mscorlib]System.Guid organizationId, string userPuid, string applicationVersion, string sqlErrorCode, string exceptionDetails, string sqlText, valuetype [mscorlib]System.Guid clientConnectionId, int32 commandTimeout, string environmentStackTrace, string entityName, string operationName, string orgDbName, string reqId)
0xe0e1  call     class Microsoft.Crm.Core.DataServices.Connection.IConnectionRetryPolicy Microsoft.Crm.CrmDbConnection::get_RetryPolicy()
0xe0e6  ldarg.s  6
0xe0e8  ldind.i4
0xe0e9  ldarg.0
0xe0ea  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Core.DataServices.Connection.IConnectionRetryPolicy::Interval(int32 currentRetries, class [mscorlib]System.Exception ex)
0xe0ef  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0xe0f4  ldarg.s  6
0xe0f6  ldarg.s  6
0xe0f8  ldind.i4
0xe0f9  ldc.i4.1
0xe0fa  add
0xe0fb  stind.i4
0xe0fc  ldarg.2
0xe0fd  ldstr    aOpenTheConnect_0// "Open the Connection (Retry)"
0xe102  call     void Microsoft.Crm.CrmDbConnection::InternalOpenWithRetry(class [System.Data]System.Data.IDbConnection connection, string descriptionText)
0xe107  call     class Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::get_Instance()
0xe10c  ldstr    aConnectionopen// "ConnectionOpened"
0xe111  ldarg.2
0xe112  ldloc.0
0xe113  callvirt instance class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0xe118  callvirt instance void Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::ConnectionEstablished(string eventName, class [System.Data]System.Data.IDbConnection connection, class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0xe11d  call     void Microsoft.Crm.CrmDbConnection::IncrementRetryCounter()
0xe122  call     class Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::get_Instance()
0xe127  ldarg.0
0xe128  ldarg.2
0xe129  ldarg.s  6
0xe12b  ldind.i4
0xe12c  callvirt instance void Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::ConnectionRetry(class [mscorlib]System.Exception ex, class [System.Data]System.Data.IDbConnection connection, int32 retryCount)
0xe131  ldc.i4.1
0xe132  stloc.s  7
0xe134  leave    loc_E314
0xe139  pop
0xe13a  ldc.i4.0
0xe13b  stloc.s  7
0xe13d  leave    loc_E314
0xe142  call     class Microsoft.Crm.Core.DataServices.Connection.IConnectionRetryPolicy Microsoft.Crm.CrmDbConnection::get_RetryPolicy()
0xe147  callvirt instance class Microsoft.Crm.Core.SqlAccess.ITransientErrorDetectionStrategy Microsoft.Crm.Core.DataServices.Connection.IConnectionRetryPolicy::get_RetryStrategy()
0xe14c  dup
0xe14d  brtrue.s loc_E153
0xe14f  pop
0xe150  ldc.i4.0
0xe151  br.s     loc_E159
0xe153  ldarg.0
0xe154  callvirt instance bool Microsoft.Crm.Core.SqlAccess.ITransientErrorDetectionStrategy::IsTransient(class [mscorlib]System.Exception ex)
0xe159  brfalse  loc_E217
0xe15e  call     class Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource::get_Instance()
0xe163  ldloc.3
0xe164  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OrganizationId()
0xe169  call     string Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0xe16e  call     string Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0xe173  ldloc.1
0xe174  brfalse.s loc_E18C
0xe176  ldloc.1
0xe177  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0xe17c  stloc.s  5
0xe17e  ldloca.s 5
0xe180  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe185  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xe18a  br.s     loc_E191
0xe18c  ldsfld   string [mscorlib]System.String::Empty
0xe191  ldstr    aRetryingSqlCom// "Retrying SQL command. Connection State:"...
0xe196  ldarg.2
0xe197  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.IDbConnection::get_State()
0xe19c  box      [System.Data]System.Data.ConnectionState
0xe1a1  ldarg.0
0xe1a2  call     string [mscorlib]System.String::Format(string, object, object)
0xe1a7  ldarg.1
0xe1a8  ldloc.1
0xe1a9  brfalse.s loc_E1B3
0xe1ab  ldloc.1
0xe1ac  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.SqlClient.SqlException::get_ClientConnectionId()
0xe1b1  br.s     loc_E1C3
0xe1b3  ldloc.2
0xe1b4  brfalse.s loc_E1BE
0xe1b6  ldloc.2
0xe1b7  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.SqlClient.SqlConnection::get_ClientConnectionId()
0xe1bc  br.s     loc_E1C3
0xe1be  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe1c3  ldarg.s  5
0xe1c5  call     string [mscorlib]System.Environment::get_StackTrace()
0xe1ca  ldloc.3
0xe1cb  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_EntityName()
0xe1d0  ldloc.3
0xe1d1  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OperationName()
0xe1d6  ldarg.2
0xe1d7  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0xe1dc  call     string Microsoft.Crm.MetricsReporting::get_CurrentRequestId()
0xe1e1  callvirt instance void Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource::DBExceptionDiagnostics(valuetype [mscorlib]System.Guid organizationId, string userPuid, string applicationVersion, string sqlErrorCode, string exceptionDetails, string sqlText, valuetype [mscorlib]System.Guid clientConnectionId, int32 commandTimeout, string environmentStackTrace, string entityName, string operationName, string orgDbName, string reqId)
0xe1e6  call     class Microsoft.Crm.Core.DataServices.Connection.IConnectionRetryPolicy Microsoft.Crm.CrmDbConnection::get_RetryPolicy()
0xe1eb  ldarg.s  6
0xe1ed  ldind.i4
0xe1ee  ldarg.0
0xe1ef  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Core.DataServices.Connection.IConnectionRetryPolicy::Interval(int32 currentRetries, class [mscorlib]System.Exception ex)
0xe1f4  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0xe1f9  ldarg.s  6
0xe1fb  ldarg.s  6
0xe1fd  ldind.i4
0xe1fe  ldc.i4.1
0xe1ff  add
0xe200  stind.i4
0xe201  call     void Microsoft.Crm.CrmDbConnection::IncrementRetryCounter()
0xe206  call     class Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::get_Instance()
0xe20b  ldarg.0
0xe20c  ldarg.2
0xe20d  ldarg.s  6
0xe20f  ldind.i4
0xe210  callvirt instance void Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::ConnectionRetry(class [mscorlib]System.Exception ex, class [System.Data]System.Data.IDbConnection connection, int32 retryCount)
0xe215  ldc.i4.1
0xe216  ret
0xe217  ldloc.1
0xe218  brfalse.s loc_E26D
0xe21a  ldloc.1
0xe21b  call     instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0xe220  ldc.i4.s 0xFE
0xe222  bne.un.s loc_E26D
0xe224  ldarg.2
0xe225  callvirt instance string [System.Data]System.Data.IDbConnection::get_ConnectionString()
0xe22a  call     string Microsoft.Crm.CrmDirectSqlConnection::ExtractServerNameFromConnectionString(string connectionString)
0xe22f  stloc.s  8
0xe231  ldnull
0xe232  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xe237  ldc.i4.s 0x1D
0xe239  ldstr    aTimeoutExpired// "Timeout expired: Server: {0}, Database:"...
0xe23e  ldc.i4.5
0xe23f  newarr   [mscorlib]System.Object
0xe244  dup
0xe245  ldc.i4.0
0xe246  ldloc.s  8
0xe248  stelem.ref
0xe249  dup
0xe24a  ldc.i4.1
0xe24b  ldarg.2
0xe24c  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0xe251  stelem.ref
0xe252  dup
0xe253  ldc.i4.2
0xe254  ldarg.2
0xe255  callvirt instance int32 [System.Data]System.Data.IDbConnection::get_ConnectionTimeout()
0xe25a  box      [mscorlib]System.Int32
0xe25f  stelem.ref
0xe260  dup
0xe261  ldc.i4.3
0xe262  ldarg.1
0xe263  stelem.ref
0xe264  dup
0xe265  ldc.i4.4
0xe266  ldarg.0
0xe267  stelem.ref
0xe268  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0xe26d  call     class Microsoft.Crm.MetricsReporting Microsoft.Crm.MetricsReporting::get_Instance()
0xe272  ldstr    aSqlfailedqueri// "SqlFailedQueries"
0xe277  ldloc.0
0xe278  callvirt instance int64 Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedTicks()
0xe27d  conv.r8
0xe27e  ldc.r8   10000.0
0xe287  div
0xe288  ldnull
0xe289  callvirt instance class Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric Microsoft.Crm.MetricsReporting::AddCounterMetric(string name, float64 value, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xe28e  pop
0xe28f  call     class Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource::get_Instance()
0xe294  ldloc.3
0xe295  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OrganizationId()
0xe29a  call     string Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0xe29f  call     string Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0xe2a4  ldloc.1
0xe2a5  brfalse.s loc_E2BD
0xe2a7  ldloc.1
0xe2a8  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0xe2ad  stloc.s  5
0xe2af  ldloca.s 5
0xe2b1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe2b6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xe2bb  br.s     loc_E2C2
0xe2bd  ldsfld   string [mscorlib]System.String::Empty
0xe2c2  ldstr    aIntransaction0// "InTransaction: {0}, Exception: {1}"
0xe2c7  ldarg.3
0xe2c8  box      [mscorlib]System.Boolean
0xe2cd  ldarg.0
0xe2ce  call     string [mscorlib]System.String::Format(string, object, object)
0xe2d3  ldarg.1
0xe2d4  ldloc.1
0xe2d5  brfalse.s loc_E2DF
0xe2d7  ldloc.1
0xe2d8  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.SqlClient.SqlException::get_ClientConnectionId()
0xe2dd  br.s     loc_E2EF
0xe2df  ldloc.2
0xe2e0  brfalse.s loc_E2EA
0xe2e2  ldloc.2
0xe2e3  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.SqlClient.SqlConnection::get_ClientConnectionId()
0xe2e8  br.s     loc_E2EF
0xe2ea  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe2ef  ldarg.s  5
0xe2f1  call     string [mscorlib]System.Environment::get_StackTrace()
0xe2f6  ldloc.3
0xe2f7  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_EntityName()
0xe2fc  ldloc.3
0xe2fd  callvirt instance string Microsoft.Crm.Core.DataServices.DataPerformance.QueryDetails::get_OperationName()
0xe302  ldarg.2
0xe303  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0xe308  call     string Microsoft.Crm.MetricsReporting::get_CurrentRequestId()
0xe30d  callvirt instance void Microsoft.Crm.Core.Diagnostics.EventSources.CoreDiagnosticsEventSource::DBExceptionDiagnostics(valuetype [mscorlib]System.Guid organizationId, string userPuid, string applicationVersion, string sqlErrorCode, string exceptionDetails, string sqlText, valuetype [mscorlib]System.Guid clientConnectionId, int32 commandTimeout, string environmentStackTrace, string entityName, string operationName, string orgDbName, string reqId)
0xe312  ldc.i4.0
0xe313  ret
0xe314  ldloc.s  7
0xe316  ret
  ... truncated ...
```
