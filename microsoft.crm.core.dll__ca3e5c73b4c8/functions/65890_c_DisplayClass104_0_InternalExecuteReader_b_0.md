# <>c__DisplayClass104_0::<InternalExecuteReader>b__0

- ea: `0x65890`
- end: `0x65a14`
- name: `<>c__DisplayClass104_0::<InternalExecuteReader>b__0`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0xcc70`
- `0x1eaa0`
- `0x1f4d0`
- `0x331c0`
- `0x331e0`
- `0x55d00`
- `0x5aec0`
- `0x5af20`
- `0x5de00`
- `0x65890`

## string_xrefs

- `0x659ea`: `DataReaderCompleted`
- `0x658a0`: `MSCRM_CONFIG`
- `0x658bc`: `mscrm_config_sitewide`
- `0x659f6`: `Error executing reader`

## pseudocode

```c

```

## disassembly

```asm
0x65890  ldarg.0
0x65891  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass104_0::command
0x65896  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x6589b  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0x658a0  ldstr    aMscrmConfig// "MSCRM_CONFIG"
0x658a5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x658aa  brtrue.s loc_658C8
0x658ac  ldarg.0
0x658ad  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass104_0::command
0x658b2  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x658b7  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0x658bc  ldstr    aMscrmConfigSit// "mscrm_config_sitewide"
0x658c1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x658c6  brfalse.s loc_65923
0x658c8  ldarg.0
0x658c9  ldfld    string <>c__DisplayClass104_0::sourceFilePath
0x658ce  ldstr    aCrmdbconnectio_1// "CrmDbConnection.cs"
0x658d3  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x658d8  brtrue.s loc_65923
0x658da  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CrmServiceName
0x658df  call     string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::get_ServiceIdentifier()
0x658e4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x658e9  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Caller
0x658ee  ldarg.0
0x658ef  ldfld    string <>c__DisplayClass104_0::memberName
0x658f4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x658f9  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerSourceFile
0x658fe  ldarg.0
0x658ff  ldfld    string <>c__DisplayClass104_0::sourceFilePath
0x65904  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x65909  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6590e  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CallerLineNumber
0x65913  ldarg.0
0x65914  ldflda   int32 <>c__DisplayClass104_0::sourceLineNumber
0x65919  call     instance string [mscorlib]System.Int32::ToString()
0x6591e  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65923  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Database
0x65928  ldarg.0
0x65929  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass104_0::command
0x6592e  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x65933  callvirt instance string [System.Data]System.Data.IDbConnection::get_Database()
0x65938  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x6593d  ldsfld   string Microsoft.Crm.CustomPropertyConstants::Command
0x65942  ldarg.0
0x65943  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass104_0::command
0x65948  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x6594d  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x65952  newobj   instance void Microsoft.Crm.TimeTracker::.ctor()
0x65957  stloc.0
0x65958  newobj   instance void Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x6595d  stloc.1
0x6595e  ldsfld   string [mscorlib]System.String::Empty
0x65963  stloc.2
0x65964  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x65969  ldc.i4.s 0x1D
0x6596b  ldstr    a0// "{0}"
0x65970  ldc.i4.1
0x65971  newarr   [mscorlib]System.Object
0x65976  dup
0x65977  ldc.i4.0
0x65978  ldarg.0
0x65979  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass104_0::command
0x6597e  stelem.ref
0x6597f  call     void Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x65984  ldloc.0
0x65985  callvirt instance void Microsoft.Crm.TimeTracker::Start()
0x6598a  ldarg.0
0x6598b  ldflda   valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.CommandBehavior> <>c__DisplayClass104_0::commandBehavior
0x65990  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.CommandBehavior>::get_HasValue()
0x65995  brtrue.s loc_659AC
0x65997  ldarg.0
0x65998  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass104_0::command
0x6599d  dup
0x6599e  ldvirtftn instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x659a4  newobj   instance void class [mscorlib]System.Func`1<class [System.Data]System.Data.IDataReader>::.ctor(object, native int)
0x659a9  stloc.3
0x659aa  br.s     loc_659CE
0x659ac  ldarg.0
0x659ad  ldfld    class [mscorlib]System.Func`1<class [System.Data]System.Data.IDataReader> <>c__DisplayClass104_0::<>9__1
0x659b2  dup
0x659b3  brtrue.s loc_659CD
0x659b5  pop
0x659b6  ldarg.0
0x659b7  ldarg.0
0x659b8  ldftn    instance class [System.Data]System.Data.IDataReader <>c__DisplayClass104_0::<InternalExecuteReader>b__1()
0x659be  newobj   instance void class [mscorlib]System.Func`1<class [System.Data]System.Data.IDataReader>::.ctor(object, native int)
0x659c3  dup
0x659c4  stloc.s  4
0x659c6  stfld    class [mscorlib]System.Func`1<class [System.Data]System.Data.IDataReader> <>c__DisplayClass104_0::<>9__1
0x659cb  ldloc.s  4
0x659cd  stloc.3
0x659ce  ldloc.3
0x659cf  ldarg.0
0x659d0  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass104_0::command
0x659d5  call     T0x2B000123
0x659da  ldarg.0
0x659db  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass104_0::command
0x659e0  ldloc.1
0x659e1  newobj   instance void Microsoft.Crm.CrmDataReader::.ctor(class [System.Data]System.Data.IDataReader dataReader, class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x659e6  stloc.s  5
0x659e8  leave.s  loc_65A11
0x659ea  ldstr    aDatareadercomp// "DataReaderCompleted"
0x659ef  ldarg.0
0x659f0  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass104_0::command
0x659f5  ldloc.1
0x659f6  ldstr    aErrorExecuting_0// "Error executing reader"
0x659fb  call     string Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::ExceptionHandler(class [mscorlib]System.Exception exception, string eventName, class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken, string error)
0x65a00  stloc.2
0x65a01  rethrow
0x65a03  ldarg.0
0x65a04  ldfld    class [System.Data]System.Data.IDbCommand <>c__DisplayClass104_0::command
0x65a09  ldloc.0
0x65a0a  ldloc.2
0x65a0b  call     void Microsoft.Crm.Core.DataServices.Connection.CrmSqlDataAccessHelper::TrackExecutionTime(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.TimeTracker timer, string errorCode)
0x65a10  endfinally
0x65a11  ldloc.s  5
0x65a13  ret
```
