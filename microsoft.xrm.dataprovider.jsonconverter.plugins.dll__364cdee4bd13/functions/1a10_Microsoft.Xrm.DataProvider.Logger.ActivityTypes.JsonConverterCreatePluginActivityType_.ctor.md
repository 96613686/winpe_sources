# Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterCreatePluginActivityType::.ctor

- ea: `0x1a10`
- end: `0x1a28`
- name: `Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterCreatePluginActivityType::.ctor`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1b00`
- `0x1b10`

## string_xrefs

- `0x1a11`: `JsonConverterCreatePlugin`

## pseudocode

```c

```

## disassembly

```asm
0x1a10  ldarg.0
0x1a11  ldstr    aJsonconverterc// "JsonConverterCreatePlugin"
0x1a16  call     bool Microsoft.Xrm.DataProvider.Logger.ActivityTypes.Metric::get_OptOutOfDurationMetric()
0x1a1b  call     bool Microsoft.Xrm.DataProvider.Logger.ActivityTypes.Metric::get_OptOutOfConcurrentMetric()
0x1a20  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterCreatePluginActivityType>::.ctor(string, bool, bool)
0x1a25  nop
0x1a26  nop
0x1a27  ret
```
