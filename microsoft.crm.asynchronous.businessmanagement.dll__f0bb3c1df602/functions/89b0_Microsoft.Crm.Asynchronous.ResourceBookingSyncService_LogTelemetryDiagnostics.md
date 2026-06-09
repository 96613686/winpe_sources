# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::LogTelemetryDiagnostics

- ea: `0x89b0`
- end: `0x8a53`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::LogTelemetryDiagnostics`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5da0`

## callees

- `0x8ab0`
- `0x16330`
- `0x16430`
- `0x164d0`

## string_xrefs

- `0x89e3`: `NumberOfAppointmentsForCreateSync`
- `0x8a13`: `NumberOfAppointmentsForCreateSyncError`
- `0x89f3`: `NumberOfAppointmentsForUpdateSync`
- `0x8a23`: `NumberOfAppointmentsForUpdateSyncError`
- `0x8a03`: `NumberOfAppointmentsForDeleteSync`
- `0x8a33`: `NumberOfAppointmentsForDeleteSyncError`

## pseudocode

```c

```

## disassembly

```asm
0x89b0  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x89b5  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x89ba  ldarg.0
0x89bb  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x89c0  ldstr    aIsresourcebook// "IsResourceBookingSyncEnabled"
0x89c5  callvirt instance int32 Metrics::GetValue(string name)
0x89ca  ldc.i4.1
0x89cb  ceq
0x89cd  ldarg.0
0x89ce  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x89d3  ldstr    aUsers// "Users"
0x89d8  callvirt instance int32 Metrics::GetSetCount(string name)
0x89dd  ldarg.0
0x89de  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x89e3  ldstr    aNumberofappoin// "NumberOfAppointmentsForCreateSync"
0x89e8  callvirt instance int32 Metrics::GetValue(string name)
0x89ed  ldarg.0
0x89ee  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x89f3  ldstr    aNumberofappoin_2// "NumberOfAppointmentsForUpdateSync"
0x89f8  callvirt instance int32 Metrics::GetValue(string name)
0x89fd  ldarg.0
0x89fe  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8a03  ldstr    aNumberofappoin_7// "NumberOfAppointmentsForDeleteSync"
0x8a08  callvirt instance int32 Metrics::GetValue(string name)
0x8a0d  ldarg.0
0x8a0e  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8a13  ldstr    aNumberofappoin_1// "NumberOfAppointmentsForCreateSyncError"
0x8a18  callvirt instance int32 Metrics::GetValue(string name)
0x8a1d  ldarg.0
0x8a1e  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8a23  ldstr    aNumberofappoin_4// "NumberOfAppointmentsForUpdateSyncError"
0x8a28  callvirt instance int32 Metrics::GetValue(string name)
0x8a2d  ldarg.0
0x8a2e  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8a33  ldstr    aNumberofappoin_8// "NumberOfAppointmentsForDeleteSyncError"
0x8a38  callvirt instance int32 Metrics::GetValue(string name)
0x8a3d  ldarg.0
0x8a3e  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8a43  ldstr    aResourcebookin// "ResourceBookingSync"
0x8a48  callvirt instance string Metrics::GetElapsedTime(string name)
0x8a4d  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogResourceBookingSyncDiagnostics(valuetype [mscorlib]System.Guid, bool, int32, int32, int32, int32, int32, int32, int32, string)
0x8a52  ret
```
