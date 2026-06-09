# Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterUpdatePluginActivityType::.ctor

- ea: `0x1ad0`
- end: `0x1ae8`
- name: `Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterUpdatePluginActivityType::.ctor`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1b00`
- `0x1b10`

## string_xrefs

- `0x1ad1`: `JsonConverterUpdatePlugin`

## pseudocode

```c

```

## disassembly

```asm
0x1ad0  ldarg.0
0x1ad1  ldstr    aJsonconverteru// "JsonConverterUpdatePlugin"
0x1ad6  call     bool Microsoft.Xrm.DataProvider.Logger.ActivityTypes.Metric::get_OptOutOfDurationMetric()
0x1adb  call     bool Microsoft.Xrm.DataProvider.Logger.ActivityTypes.Metric::get_OptOutOfConcurrentMetric()
0x1ae0  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterUpdatePluginActivityType>::.ctor(string, bool, bool)
0x1ae5  nop
0x1ae6  nop
0x1ae7  ret
```
