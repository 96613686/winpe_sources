# Microsoft.Crm.CrmDbConnection::GetCreateAndOpenConnection

- ea: `0xdc90`
- end: `0xdd82`
- name: `Microsoft.Crm.CrmDbConnection::GetCreateAndOpenConnection`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0xd2f0`

## callees

- `0xd140`
- `0xdc90`
- `0xdd90`
- `0xddb0`
- `0xec30`
- `0xf260`
- `0xf530`
- `0xf550`
- `0xf5b0`
- `0x1c220`
- `0x1c350`
- `0x54770`
- `0x54a10`
- `0x55cd0`
- `0x55d00`
- `0x55d20`
- `0x57ae0`

## string_xrefs

- `0xdcc8`: `Open the Connection`
- `0xdcea`: `Connection failed to open for connection string: `
- `0xdd16`: `Connection opened for connection string: `
- `0xdd53`: `SqlConnectionOpens`
- `0xdd75`: `ConnectionOpened`

## pseudocode

```c

```

## disassembly

```asm
0xdc90  ldarg.0
0xdc91  call     instance class [System.Data]System.Data.SqlClient.SqlConnection Microsoft.Crm.CrmDbConnection::GetCreateConnection()
0xdc96  stloc.0
0xdc97  newobj   instance void Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0xdc9c  stloc.1
0xdc9d  call     class Microsoft.Crm.CrmSqlAuthenticationProviderFactory Microsoft.Crm.CrmSqlAuthenticationProviderFactory::get_Instance()
0xdca2  ldarg.0
0xdca3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmDbConnection::_organizationId
0xdca8  ldc.i4.0
0xdca9  callvirt instance class Microsoft.Crm.ICrmSqlAuthenticationProvider Microsoft.Crm.CrmSqlAuthenticationProviderFactory::GetAuthenticationProvider(valuetype [mscorlib]System.Guid organizationId, valuetype Microsoft.Crm.ConnectionAccessType connectionAccessType)
0xdcae  ldloc.0
0xdcaf  callvirt instance void Microsoft.Crm.ICrmSqlAuthenticationProvider::Apply(class [System.Data]System.Data.SqlClient.SqlConnection connection)
0xdcb4  ldloca.s 2
0xdcb6  ldarg.0
0xdcb7  ldftn    instance void Microsoft.Crm.CrmDbConnection::<GetCreateAndOpenConnection>b__100_0(valuetype [mscorlib]System.TimeSpan ts)
0xdcbd  newobj   instance void class [mscorlib]System.Action`1<valuetype [mscorlib]System.TimeSpan>::.ctor(object, native int)
0xdcc2  call     instance void Microsoft.Crm.Core.SqlAccess.ExecutionStopwatch::.ctor(class [mscorlib]System.Action`1<valuetype [mscorlib]System.TimeSpan> logExecutionTime)
0xdcc7  ldloc.0
0xdcc8  ldstr    aOpenTheConnect// "Open the Connection"
0xdccd  call     void Microsoft.Crm.CrmDbConnection::InternalOpenWithRetry(class [System.Data]System.Data.IDbConnection connection, string descriptionText)
0xdcd2  leave.s  loc_DCE2
0xdcd4  ldloca.s 2
0xdcd6  constrained. Microsoft.Crm.Core.SqlAccess.ExecutionStopwatch
0xdcdc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdce1  endfinally
0xdce2  leave.s  loc_DD11
0xdce4  pop
0xdce5  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.CrmDbConnection::_logger
0xdcea  ldstr    aConnectionFail// "Connection failed to open for connectio"...
0xdcef  ldarg.0
0xdcf0  ldfld    class [mscorlib]System.Lazy`1<class Microsoft.Crm.CrmSqlAccessConfigurationBuilder> Microsoft.Crm.CrmDbConnection::sqlAccessConfigBuilder
0xdcf5  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.CrmSqlAccessConfigurationBuilder>::get_Value()
0xdcfa  callvirt instance string Microsoft.Crm.CrmSqlAccessConfigurationBuilder::get_ConnectionStringWithPasswordMashed()
0xdcff  call     string [mscorlib]System.String::Concat(string, string)
0xdd04  ldc.i4.0
0xdd05  newarr   [mscorlib]System.Object
0xdd0a  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xdd0f  rethrow
0xdd11  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.CrmDbConnection::_logger
0xdd16  ldstr    aConnectionOpen// "Connection opened for connection string"...
0xdd1b  ldarg.0
0xdd1c  ldfld    class [mscorlib]System.Lazy`1<class Microsoft.Crm.CrmSqlAccessConfigurationBuilder> Microsoft.Crm.CrmDbConnection::sqlAccessConfigBuilder
0xdd21  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.CrmSqlAccessConfigurationBuilder>::get_Value()
0xdd26  callvirt instance string Microsoft.Crm.CrmSqlAccessConfigurationBuilder::get_ConnectionStringWithPasswordMashed()
0xdd2b  call     string [mscorlib]System.String::Concat(string, string)
0xdd30  ldc.i4.0
0xdd31  newarr   [mscorlib]System.Object
0xdd36  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xdd3b  ldloc.0
0xdd3c  ldarg.0
0xdd3d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmDbConnection::get_OrganizationId()
0xdd42  call     void Microsoft.Crm.CrmOrgDbConnectionManager::HandleOpen(class [System.Data]System.Data.IDbConnection connection, valuetype [mscorlib]System.Guid organizationId)
0xdd47  ldloc.1
0xdd48  callvirt instance class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0xdd4d  pop
0xdd4e  call     class Microsoft.Crm.MetricsReporting Microsoft.Crm.MetricsReporting::get_Instance()
0xdd53  ldstr    aSqlconnectiono// "SqlConnectionOpens"
0xdd58  ldloc.1
0xdd59  callvirt instance int64 Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedTicks()
0xdd5e  conv.r8
0xdd5f  ldc.r8   10000.0
0xdd68  div
0xdd69  ldnull
0xdd6a  callvirt instance class Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric Microsoft.Crm.MetricsReporting::AddCounterMetric(string name, float64 value, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0xdd6f  pop
0xdd70  call     class Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::get_Instance()
0xdd75  ldstr    aConnectionopen// "ConnectionOpened"
0xdd7a  ldarg.0
0xdd7b  ldloc.1
0xdd7c  callvirt instance void Microsoft.Crm.Core.Telemetry.EventSources.DatabaseTelemetryEvents::ConnectionEstablished(string eventName, class [System.Data]System.Data.IDbConnection connection, class Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0xdd81  ret
```
