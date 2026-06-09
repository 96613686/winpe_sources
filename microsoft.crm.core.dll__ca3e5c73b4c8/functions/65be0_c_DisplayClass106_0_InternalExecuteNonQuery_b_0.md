# <>c__DisplayClass106_0::<InternalExecuteNonQuery>b__0

- ea: `0x65be0`
- end: `0x65d66`
- name: `<>c__DisplayClass106_0::<InternalExecuteNonQuery>b__0`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe420`
- `0x1eaa0`
- `0x1f4d0`
- `0x331c0`
- `0x331e0`
- `0x54770`
- `0x548c0`
- `0x55d00`
- `0x55d20`
- `0x5aec0`
- `0x5af20`
- `0x5de00`
- `0x65be0`

## string_xrefs

- `0x65cfc`: `CommandCompleted`
- `0x65d17`: `CommandCompleted`
- `0x65bf0`: `MSCRM_CONFIG`
- `0x65c0c`: `mscrm_config_sitewide`

## pseudocode

```c

```

## disassembly

```asm
0x65be0  ldarg.0
0x65be1  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass106_0::command
0x65be6  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x65beb  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0x65bf0  ldstr    aMscrmConfig// "MSCRM_CONFIG"
0x65bf5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x65bfa  brtrue.s loc_65C18
0x65bfc  ldarg.0
0x65bfd  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass106_0::command
0x65c02  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x65c07  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0x65c0c  ldstr    aMscrmConfigSit// "mscrm_config_sitewide"
0x65c11  call     bool [mscorlib]System.String::op_Equality(string, string)
0x65c16  brfalse.s loc_65C73
0x65c18  ldarg.0
0x65c19  ldfld    string <>c__DisplayClass106_0::sourceFilePath
0x65c1e  ldstr    aCrmdbconnectio_1// "CrmDbConnection.cs"
0x65c23  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x65c28  brtrue.s loc_65C73
0x65c2a  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CrmServiceName
0x65c2f  call     string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::get_ServiceIdentifier()
0x65c34  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65c39  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Caller
0x65c3e  ldarg.0
0x65c3f  ldfld    string <>c__DisplayClass106_0::memberName
0x65c44  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65c49  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerSourceFile
0x65c4e  ldarg.0
0x65c4f  ldfld    string <>c__DisplayClass106_0::sourceFilePath
0x65c54  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x65c59  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65c5e  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerLineNumber
0x65c63  ldarg.0
0x65c64  ldflda   int32 <>c__DisplayClass106_0::sourceLineNumber
0x65c69  call     instance string [mscorlib]System.Int32::ToString()
0x65c6e  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65c73  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Database
0x65c78  ldarg.0
0x65c79  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass106_0::command
0x65c7e  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x65c83  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0x65c88  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65c8d  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Command
0x65c92  ldarg.0
0x65c93  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass106_0::command
0x65c98  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x65c9d  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65ca2  newobj   instance void Microsoft.Crm.TimeTracker::.ctor()
0x65ca7  stloc.0
0x65ca8  newobj   instance void Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x65cad  stloc.1
0x65cae  ldsfld   string [mscorlib]System.String::Empty
0x65cb3  stloc.2
0x65cb4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x65cb9  ldc.i4.s 0x1D
0x65cbb  ldstr    a0// "{0}"
0x65cc0  ldc.i4.1
0x65cc1  newarr   [mscorlib]System.Object
0x65cc6  dup
0x65cc7  ldc.i4.0
0x65cc8  ldarg.0
0x65cc9  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass106_0::command
0x65cce  stelem.ref
0x65ccf  call     void Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x65cd4  ldloc.0
0x65cd5  callvirt instance void Microsoft.Crm.TimeTracker::Start()
0x65cda  ldarg.0
0x65cdb  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass106_0::command
0x65ce0  dup
0x65ce1  ldvirtftn instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x65ce7  newobj   instance void class [mscorlib]System.Func`1<int32>::.ctor(object, native int)
0x65cec  ldarg.0
0x65ced  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass106_0::command
0x65cf2  call     T0x2B000125
0x65cf7  call     class Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::get_Instance()
0x65cfc  ldstr    aCommandcomplet// "CommandCompleted"
0x65d01  ldarg.0
0x65d02  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass106_0::command
0x65d07  ldc.i4.1
0x65d08  ldloc.1
0x65d09  callvirt instance class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x65d0e  callvirt instance void Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::CommandExecuted(string eventName, class [System.Data]System.Data.IDbCommand command, bool includeCommandText, class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x65d13  stloc.3
0x65d14  leave.s  loc_65D64
0x65d16  dup
0x65d17  ldstr    aCommandcomplet// "CommandCompleted"
0x65d1c  ldarg.0
0x65d1d  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass106_0::command
0x65d22  ldloc.1
0x65d23  ldstr    aErrorExecuting_2// "Error executing InternalExecuteNonQuery"
0x65d28  call     string Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::ExceptionHandler(class [mscorlib]System.Exception exception, string eventName, class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken, string error)
0x65d2d  stloc.2
0x65d2e  isinst   [System.Data]System.Data.SqlClient.SqlException
0x65d33  stloc.s  4
0x65d35  ldloc.s  4
0x65d37  brfalse.s loc_65D54
0x65d39  ldloc.s  4
0x65d3b  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x65d40  ldc.i4   0x2BD
0x65d45  bne.un.s loc_65D54
0x65d47  ldarg.0
0x65d48  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass106_0::command
0x65d4d  ldloc.s  4
0x65d4f  call     void Microsoft.Crm.CrmDbConnection::LogDBCCMemoryStatus(class [System.Data]System.Data.IDbCommand command, class [System.Data]System.Data.SqlClient.SqlException exception)
0x65d54  rethrow
0x65d56  ldarg.0
0x65d57  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass106_0::command
0x65d5c  ldloc.0
0x65d5d  ldloc.2
0x65d5e  call     void Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::TrackExecutionTime(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.TimeTracker timer, string errorCode)
0x65d63  endfinally
0x65d64  ldloc.3
0x65d65  ret
```
