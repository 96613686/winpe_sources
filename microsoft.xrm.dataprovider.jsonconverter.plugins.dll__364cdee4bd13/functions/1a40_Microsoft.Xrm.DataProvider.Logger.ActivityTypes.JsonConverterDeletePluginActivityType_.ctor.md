# Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterDeletePluginActivityType::.ctor

- ea: `0x1a40`
- end: `0x1a58`
- name: `Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterDeletePluginActivityType::.ctor`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1b00`
- `0x1b10`

## string_xrefs

- `0x1a41`: `JsonConverterDeletePlugin`

## pseudocode

```c

```

## disassembly

```asm
0x1a40  ldarg.0
0x1a41  ldstr    aJsonconverterd// "JsonConverterDeletePlugin"
0x1a46  call     bool Microsoft.Xrm.DataProvider.Logger.ActivityTypes.Metric::get_OptOutOfDurationMetric()
0x1a4b  call     bool Microsoft.Xrm.DataProvider.Logger.ActivityTypes.Metric::get_OptOutOfConcurrentMetric()
0x1a50  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterDeletePluginActivityType>::.ctor(string, bool, bool)
0x1a55  nop
0x1a56  nop
0x1a57  ret
```
