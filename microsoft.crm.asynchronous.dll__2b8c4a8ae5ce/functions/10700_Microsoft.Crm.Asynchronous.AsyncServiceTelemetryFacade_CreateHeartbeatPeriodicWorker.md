# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryFacade::CreateHeartbeatPeriodicWorker

- ea: `0x10700`
- end: `0x10712`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryFacade::CreateHeartbeatPeriodicWorker`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x105f0`
- `0x106f0`
- `0x14870`

## pseudocode

```c

```

## disassembly

```asm
0x10700  ldarg.1
0x10701  ldarg.0
0x10702  call     instance class Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryMetrics Microsoft.Crm.Asynchronous.AsyncServiceTelemetryFacade::get_Metrics()
0x10707  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryMetric Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryMetrics::get_Heartbeat()
0x1070c  newobj   instance void Microsoft.Crm.Asynchronous.AsyncServiceHeartbeatPeriodicWorker::.ctor(int32 period, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryMetric heartbeatMetric)
0x10711  ret
```
