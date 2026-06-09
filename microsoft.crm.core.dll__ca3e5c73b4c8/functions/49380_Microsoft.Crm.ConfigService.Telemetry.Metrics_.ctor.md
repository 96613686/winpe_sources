# Microsoft.Crm.ConfigService.Telemetry.Metrics::.ctor

- ea: `0x49380`
- end: `0x49431`
- name: `Microsoft.Crm.ConfigService.Telemetry.Metrics::.ctor`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6a690`

## callees

- `0x49230`
- `0x49250`
- `0x49270`
- `0x49290`
- `0x492b0`
- `0x492d0`
- `0x492f0`
- `0x49310`
- `0x49330`
- `0x49350`
- `0x49440`

## string_xrefs

- `0x49388`: `LocatorServiceExecutionTime`
- `0x49399`: `ConfigServiceExecutionTime`
- `0x493cc`: `FallbackToConfigService`
- `0x493dd`: `ResponseFromConfigService`

## pseudocode

```c

```

## disassembly

```asm
0x49380  ldarg.0
0x49381  call     instance void [mscorlib]System.Object::.ctor()
0x49386  ldarg.0
0x49387  ldarg.0
0x49388  ldstr    aLocatorservice_7// "LocatorServiceExecutionTime"
0x4938d  call     instance class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.ConfigService.Telemetry.Metrics::CreateMetric(string metricName)
0x49392  call     instance void Microsoft.Crm.ConfigService.Telemetry.Metrics::set_LocatorServiceExecutionTime(class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0x49397  ldarg.0
0x49398  ldarg.0
0x49399  ldstr    aConfigservicee// "ConfigServiceExecutionTime"
0x4939e  call     instance class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.ConfigService.Telemetry.Metrics::CreateMetric(string metricName)
0x493a3  call     instance void Microsoft.Crm.ConfigService.Telemetry.Metrics::set_ConfigServiceExecutionTime(class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0x493a8  ldarg.0
0x493a9  ldarg.0
0x493aa  ldstr    aTotalexecution// "TotalExecutionTime"
0x493af  call     instance class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.ConfigService.Telemetry.Metrics::CreateMetric(string metricName)
0x493b4  call     instance void Microsoft.Crm.ConfigService.Telemetry.Metrics::set_TotalExecutionTime(class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0x493b9  ldarg.0
0x493ba  ldarg.0
0x493bb  ldstr    aFallbacktosql// "FallbackToSQL"
0x493c0  call     instance class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.ConfigService.Telemetry.Metrics::CreateMetric(string metricName)
0x493c5  call     instance void Microsoft.Crm.ConfigService.Telemetry.Metrics::set_FallbackToSQL(class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0x493ca  ldarg.0
0x493cb  ldarg.0
0x493cc  ldstr    aFallbacktoconf// "FallbackToConfigService"
0x493d1  call     instance class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.ConfigService.Telemetry.Metrics::CreateMetric(string metricName)
0x493d6  call     instance void Microsoft.Crm.ConfigService.Telemetry.Metrics::set_FallbackToConfigService(class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0x493db  ldarg.0
0x493dc  ldarg.0
0x493dd  ldstr    aResponsefromco// "ResponseFromConfigService"
0x493e2  call     instance class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.ConfigService.Telemetry.Metrics::CreateMetric(string metricName)
0x493e7  call     instance void Microsoft.Crm.ConfigService.Telemetry.Metrics::set_ResponseFromConfigService(class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0x493ec  ldarg.0
0x493ed  ldarg.0
0x493ee  ldstr    aResponsefromsq// "ResponseFromSQL"
0x493f3  call     instance class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.ConfigService.Telemetry.Metrics::CreateMetric(string metricName)
0x493f8  call     instance void Microsoft.Crm.ConfigService.Telemetry.Metrics::set_ResponseFromSQL(class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0x493fd  ldarg.0
0x493fe  ldarg.0
0x493ff  ldstr    aResponsematch// "ResponseMatch"
0x49404  call     instance class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.ConfigService.Telemetry.Metrics::CreateMetric(string metricName)
0x49409  call     instance void Microsoft.Crm.ConfigService.Telemetry.Metrics::set_ResponseMatch(class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0x4940e  ldarg.0
0x4940f  ldarg.0
0x49410  ldstr    aResponsemismat// "ResponseMismatch"
0x49415  call     instance class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.ConfigService.Telemetry.Metrics::CreateMetric(string metricName)
0x4941a  call     instance void Microsoft.Crm.ConfigService.Telemetry.Metrics::set_ResponseMismatch(class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0x4941f  ldarg.0
0x49420  ldarg.0
0x49421  ldstr    aGetsettingsexe// "GetSettingsExecutionTime"
0x49426  call     instance class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric Microsoft.Crm.ConfigService.Telemetry.Metrics::CreateMetric(string metricName)
0x4942b  call     instance void Microsoft.Crm.ConfigService.Telemetry.Metrics::set_GetSettingsExecutionTime(class Microsoft.Crm.Core.Telemetry.CrmMeasureMetric value)
0x49430  ret
```
