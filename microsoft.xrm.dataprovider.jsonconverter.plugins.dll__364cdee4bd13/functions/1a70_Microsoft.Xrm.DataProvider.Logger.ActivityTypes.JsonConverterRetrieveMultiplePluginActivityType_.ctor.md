# Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterRetrieveMultiplePluginActivityType::.ctor

- ea: `0x1a70`
- end: `0x1a88`
- name: `Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterRetrieveMultiplePluginActivityType::.ctor`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1b00`
- `0x1b10`

## string_xrefs

- `0x1a71`: `JsonConverterRetrieveMultiplePlugin`

## pseudocode

```c

```

## disassembly

```asm
0x1a70  ldarg.0
0x1a71  ldstr    aJsonconverterr// "JsonConverterRetrieveMultiplePlugin"
0x1a76  call     bool Microsoft.Xrm.DataProvider.Logger.ActivityTypes.Metric::get_OptOutOfDurationMetric()
0x1a7b  call     bool Microsoft.Xrm.DataProvider.Logger.ActivityTypes.Metric::get_OptOutOfConcurrentMetric()
0x1a80  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterRetrieveMultiplePluginActivityType>::.ctor(string, bool, bool)
0x1a85  nop
0x1a86  nop
0x1a87  ret
```
