# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Run

- ea: `0x5da0`
- end: `0x5ebe`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Run`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x8b90`

## callees

- `0x5da0`
- `0x5ed0`
- `0x88e0`
- `0x89b0`
- `0x8ab0`
- `0x8af0`
- `0x13dc0`
- `0x13fb0`
- `0x13fe0`
- `0x161f0`
- `0x16370`
- `0x163a0`
- `0x163f0`
- `0x16540`
- `0x16580`

## string_xrefs

- `0x5df8`: `MSCRMResourceBookingSyncService`
- `0x5e4b`: `ResourceBookingSyncService FCB is not enabled. Nothing to do.`
- `0x5e9f`: `Exiting Resource Booking Sync Service, Org: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5da0  ldarg.0
0x5da1  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x5da6  callvirt instance int32 ConfigurationSettings::get_MaxRunTimeInMinutes()
0x5dab  call     void RunTimeControl::StartCountDown(int32 countdownInMinutes)
0x5db0  ldarg.0
0x5db1  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x5db6  ldstr    aResourcebookin// "ResourceBookingSync"
0x5dbb  ldstr    aResourceBookin// "Resource Booking Synchronization"
0x5dc0  callvirt instance class Timer Metrics::AddTimer(string name, string description)
0x5dc5  pop
0x5dc6  ldarg.0
0x5dc7  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x5dcc  ldstr    aResourcebookin// "ResourceBookingSync"
0x5dd1  ldc.i4.1
0x5dd2  callvirt instance void Metrics::StartTimer(string name, bool trace)
0x5dd7  ldarg.0
0x5dd8  call     instance bool Microsoft.Crm.Asynchronous.ResourceBookingSyncService::IsResourceBookingSyncEnabled()
0x5ddd  brfalse.s loc_5E3A
0x5ddf  ldarg.0
0x5de0  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x5de5  ldstr    aIsresourcebook// "IsResourceBookingSyncEnabled"
0x5dea  ldc.i4.1
0x5deb  callvirt instance int32 Metrics::AddValue(string name, int32 value)
0x5df0  pop
0x5df1  newobj   instance void [System]System.Diagnostics.EventLog::.ctor()
0x5df6  stloc.0
0x5df7  ldloc.0
0x5df8  ldstr    aMscrmresourceb// "MSCRMResourceBookingSyncService"
0x5dfd  callvirt instance void [System]System.Diagnostics.EventLog::set_Source(string)
0x5e02  ldarg.0
0x5e03  ldloc.0
0x5e04  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor(class [System]System.Diagnostics.EventLog)
0x5e09  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog Microsoft.Crm.Asynchronous.ResourceBookingSyncService::eventLog
0x5e0e  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x5e13  ldc.i4.s 0x14
0x5e15  ldstr    aRunningResourc// "Running Resource Booking Sync, Org: {0}"
0x5e1a  ldc.i4.1
0x5e1b  newarr   [mscorlib]System.Object
0x5e20  dup
0x5e21  ldc.i4.0
0x5e22  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x5e27  box      [mscorlib]System.Guid
0x5e2c  stelem.ref
0x5e2d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5e32  ldarg.0
0x5e33  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::RunInternal()
0x5e38  br.s     loc_5E55
0x5e3a  ldarg.0
0x5e3b  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_Context()
0x5e40  call     void class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncOperationServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UpgradingOff>::DisableResourceBookingSyncRecurringJob(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5e45  ldarg.0
0x5e46  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x5e4b  ldstr    aResourcebookin_0// "ResourceBookingSyncService FCB is not e"...
0x5e50  callvirt instance void Metrics::AddMessageAndTrace(string message)
0x5e55  leave.s  loc_5EBD
0x5e57  pop
0x5e58  rethrow
0x5e5a  ldarg.0
0x5e5b  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x5e60  ldstr    aResourcebookin// "ResourceBookingSync"
0x5e65  ldc.i4.1
0x5e66  callvirt instance void Metrics::StopTimer(string name, bool trace)
0x5e6b  ldarg.0
0x5e6c  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x5e71  ldstr    aIsruntimeexpir// "IsRunTimeExpired"
0x5e76  call     bool RunTimeControl::get_DidExpire()
0x5e7b  brtrue.s loc_5E80
0x5e7d  ldc.i4.0
0x5e7e  br.s     loc_5E81
0x5e80  ldc.i4.1
0x5e81  callvirt instance int32 Metrics::AddValue(string name, int32 value)
0x5e86  pop
0x5e87  ldarg.0
0x5e88  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x5e8d  callvirt instance void Metrics::TraceAllMetricsVerbose()
0x5e92  ldarg.0
0x5e93  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::LogTelemetryDiagnostics()
0x5e98  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x5e9d  ldc.i4.s 0x14
0x5e9f  ldstr    aExitingResourc// "Exiting Resource Booking Sync Service, "...
0x5ea4  ldc.i4.1
0x5ea5  newarr   [mscorlib]System.Object
0x5eaa  dup
0x5eab  ldc.i4.0
0x5eac  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x5eb1  box      [mscorlib]System.Guid
0x5eb6  stelem.ref
0x5eb7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5ebc  endfinally
0x5ebd  ret
```
