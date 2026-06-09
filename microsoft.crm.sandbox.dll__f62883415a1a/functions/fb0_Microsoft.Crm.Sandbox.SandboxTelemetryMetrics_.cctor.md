# Microsoft.Crm.Sandbox.SandboxTelemetryMetrics::.cctor

- ea: `0xfb0`
- end: `0x1001`
- name: `Microsoft.Crm.Sandbox.SandboxTelemetryMetrics::.cctor`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xf40`
- `0xf60`
- `0xf80`
- `0xfa0`

## string_xrefs

- `0xfdd`: `SandboxSdkClientFailed1stAttempt`

## pseudocode

```c

```

## disassembly

```asm
0xfb0  ldstr    aCrmsandbox// "CRMSandbox"
0xfb5  ldstr    aSandboxfetchpr// "SandboxFetchProxyFailureRetry"
0xfba  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::.ctor(string, string)
0xfbf  call     void Microsoft.Crm.Sandbox.SandboxTelemetryMetrics::set_SandboxFetchProxyFailureRetry(class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0xfc4  ldstr    aCrmsandbox// "CRMSandbox"
0xfc9  ldstr    aSandboxfetchpr_0// "SandboxFetchProxyGiveUp"
0xfce  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::.ctor(string, string)
0xfd3  call     void Microsoft.Crm.Sandbox.SandboxTelemetryMetrics::set_SandboxFetchProxyGiveUp(class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0xfd8  ldstr    aCrmsandbox// "CRMSandbox"
0xfdd  ldstr    aSandboxsdkclie// "SandboxSdkClientFailed1stAttempt"
0xfe2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::.ctor(string, string)
0xfe7  call     void Microsoft.Crm.Sandbox.SandboxTelemetryMetrics::set_SandboxSdkClientFailed1stAttempt(class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0xfec  ldstr    aCrmsandbox// "CRMSandbox"
0xff1  ldstr    aSandboxsdkclie_0// "SandboxSdkClientFailedAfterWakeup"
0xff6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric::.ctor(string, string)
0xffb  call     void Microsoft.Crm.Sandbox.SandboxTelemetryMetrics::set_SandboxSdkClientFailedAfterWakeup(class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0x1000  ret
```
