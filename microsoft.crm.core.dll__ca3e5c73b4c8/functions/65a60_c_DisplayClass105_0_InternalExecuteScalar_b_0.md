# <>c__DisplayClass105_0::<InternalExecuteScalar>b__0

- ea: `0x65a60`
- end: `0x65bbf`
- name: `<>c__DisplayClass105_0::<InternalExecuteScalar>b__0`
- size: `351`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

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
- `0x65a60`

## string_xrefs

- `0x65b7c`: `CommandCompleted`
- `0x65b96`: `CommandCompleted`
- `0x65a70`: `MSCRM_CONFIG`
- `0x65a8c`: `mscrm_config_sitewide`

## pseudocode

```c

```

## disassembly

```asm
0x65a60  ldarg.0
0x65a61  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass105_0::command
0x65a66  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x65a6b  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0x65a70  ldstr    aMscrmConfig// "MSCRM_CONFIG"
0x65a75  call     bool [mscorlib]System.String::op_Equality(string, string)
0x65a7a  brtrue.s loc_65A98
0x65a7c  ldarg.0
0x65a7d  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass105_0::command
0x65a82  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x65a87  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0x65a8c  ldstr    aMscrmConfigSit// "mscrm_config_sitewide"
0x65a91  call     bool [mscorlib]System.String::op_Equality(string, string)
0x65a96  brfalse.s loc_65AF3
0x65a98  ldarg.0
0x65a99  ldfld    string <>c__DisplayClass105_0::sourceFilePath
0x65a9e  ldstr    aCrmdbconnectio_1// "CrmDbConnection.cs"
0x65aa3  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x65aa8  brtrue.s loc_65AF3
0x65aaa  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CrmServiceName
0x65aaf  call     string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::get_ServiceIdentifier()
0x65ab4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65ab9  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Caller
0x65abe  ldarg.0
0x65abf  ldfld    string <>c__DisplayClass105_0::memberName
0x65ac4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65ac9  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerSourceFile
0x65ace  ldarg.0
0x65acf  ldfld    string <>c__DisplayClass105_0::sourceFilePath
0x65ad4  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x65ad9  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65ade  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerLineNumber
0x65ae3  ldarg.0
0x65ae4  ldflda   int32 <>c__DisplayClass105_0::sourceLineNumber
0x65ae9  call     instance string [mscorlib]System.Int32::ToString()
0x65aee  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65af3  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Database
0x65af8  ldarg.0
0x65af9  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass105_0::command
0x65afe  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x65b03  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0x65b08  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65b0d  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Command
0x65b12  ldarg.0
0x65b13  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass105_0::command
0x65b18  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x65b1d  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65b22  newobj   instance void Microsoft.Crm.TimeTracker::.ctor()
0x65b27  stloc.0
0x65b28  newobj   instance void Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x65b2d  stloc.1
0x65b2e  ldsfld   string [mscorlib]System.String::Empty
0x65b33  stloc.2
0x65b34  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x65b39  ldc.i4.s 0x1D
0x65b3b  ldstr    a0// "{0}"
0x65b40  ldc.i4.1
0x65b41  newarr   [mscorlib]System.Object
0x65b46  dup
0x65b47  ldc.i4.0
0x65b48  ldarg.0
0x65b49  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass105_0::command
0x65b4e  stelem.ref
0x65b4f  call     void Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x65b54  ldloc.0
0x65b55  callvirt instance void Microsoft.Crm.TimeTracker::Start()
0x65b5a  ldarg.0
0x65b5b  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass105_0::command
0x65b60  dup
0x65b61  ldvirtftn instance object [System.Data]System.Data.IDbCommand::ExecuteScalar()
0x65b67  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x65b6c  ldarg.0
0x65b6d  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass105_0::command
0x65b72  call     T0x2B000124
0x65b77  call     class Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::get_Instance()
0x65b7c  ldstr    aCommandcomplet// "CommandCompleted"
0x65b81  ldarg.0
0x65b82  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass105_0::command
0x65b87  ldc.i4.1
0x65b88  ldloc.1
0x65b89  callvirt instance class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x65b8e  callvirt instance void Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::CommandExecuted(string eventName, class [System.Data]System.Data.IDbCommand command, bool includeCommandText, class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x65b93  stloc.3
0x65b94  leave.s  loc_65BBD
0x65b96  ldstr    aCommandcomplet// "CommandCompleted"
0x65b9b  ldarg.0
0x65b9c  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass105_0::command
0x65ba1  ldloc.1
0x65ba2  ldstr    aErrorExecuting_1// "Error executing scalar"
0x65ba7  call     string Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::ExceptionHandler(class [mscorlib]System.Exception exception, string eventName, class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken, string error)
0x65bac  stloc.2
0x65bad  rethrow
0x65baf  ldarg.0
0x65bb0  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass105_0::command
0x65bb5  ldloc.0
0x65bb6  ldloc.2
0x65bb7  call     void Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::TrackExecutionTime(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.TimeTracker timer, string errorCode)
0x65bbc  endfinally
0x65bbd  ldloc.3
0x65bbe  ret
```
