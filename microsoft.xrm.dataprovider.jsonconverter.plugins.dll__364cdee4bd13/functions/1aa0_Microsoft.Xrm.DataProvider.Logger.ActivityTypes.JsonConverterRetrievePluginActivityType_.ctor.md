# Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterRetrievePluginActivityType::.ctor

- ea: `0x1aa0`
- end: `0x1ab8`
- name: `Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterRetrievePluginActivityType::.ctor`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1b00`
- `0x1b10`

## string_xrefs

- `0x1aa1`: `JsonConverterRetrievePlugin`

## pseudocode

```c

```

## disassembly

```asm
0x1aa0  ldarg.0
0x1aa1  ldstr    aJsonconverterr_0// "JsonConverterRetrievePlugin"
0x1aa6  call     bool Microsoft.Xrm.DataProvider.Logger.ActivityTypes.Metric::get_OptOutOfDurationMetric()
0x1aab  call     bool Microsoft.Xrm.DataProvider.Logger.ActivityTypes.Metric::get_OptOutOfConcurrentMetric()
0x1ab0  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterRetrievePluginActivityType>::.ctor(string, bool, bool)
0x1ab5  nop
0x1ab6  nop
0x1ab7  ret
```
