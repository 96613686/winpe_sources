# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryMetrics::.ctor

- ea: `0x117e0`
- end: `0x11850`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryMetrics::.ctor`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14d40`

## callees

- `0x11880`
- `0x14bf0`

## string_xrefs

- `0x117ec`: `Service Heartbeat`

## pseudocode

```c

```

## disassembly

```asm
0x117e0  ldarg.0
0x117e1  call     instance void [mscorlib]System.Object::.ctor()
0x117e6  ldarg.0
0x117e7  ldstr    aCrmasync// "CRMAsync"
0x117ec  ldstr    aServiceHeartbe// "Service Heartbeat"
0x117f1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::.ctor(string, string)
0x117f6  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryMetric Microsoft.Crm.Asynchronous.AsyncServiceTelemetryMetrics::heartbeat
0x117fb  ldarg.0
0x117fc  ldstr    aCrmasync// "CRMAsync"
0x11801  ldstr    aScaleGroupBack// "Scale Group Backlogged Orgs Count"
0x11806  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::.ctor(string, string)
0x1180b  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryMetric Microsoft.Crm.Asynchronous.AsyncServiceTelemetryMetrics::scaleGroupBackloggedOrgsCount
0x11810  ldarg.0
0x11811  ldstr    aCrmasync// "CRMAsync"
0x11816  ldstr    aJobsExceedingQ// "Jobs Exceeding Queue Wait Time"
0x1181b  newobj   instance void Microsoft.Crm.Asynchronous.JobsExceedingQueueWaitTimeMetric::.ctor(string metricNamespace, string metricName)
0x11820  stfld    class Microsoft.Crm.Asynchronous.IJobsExceedingQueueWaitTimeMetric Microsoft.Crm.Asynchronous.AsyncServiceTelemetryMetrics::jobsExceedingQueueWaitTime
0x11825  ldarg.0
0x11826  ldstr    aCrmasync// "CRMAsync"
0x1182b  ldstr    aAsyncTimeUntil// "Async Time Until Lock Expires"
0x11830  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::.ctor(string, string)
0x11835  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryMetric Microsoft.Crm.Asynchronous.AsyncServiceTelemetryMetrics::timeUntilLock
0x1183a  ldarg.0
0x1183b  ldstr    aCrmasync// "CRMAsync"
0x11840  ldstr    aLockedDownOrgS// "Locked Down Org Starvation"
0x11845  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::.ctor(string, string)
0x1184a  call     instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryMetrics::set_LockedDownOrgStarvation(class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryMetric value)
0x1184f  ret
```
