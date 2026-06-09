# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterDeletePlugin::Execute

- ea: `0xb00`
- end: `0xb51`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterDeletePlugin::Execute`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xe0`
- `0x120`
- `0x1d0`
- `0x16b0`
- `0x1e50`

## string_xrefs

- `0xb15`: `JsonConverterDeletePlugin`

## pseudocode

```c

```

## disassembly

```asm
0xb00  newobj   instance void <>c__DisplayClass0_0::.ctor()
0xb05  stloc.0
0xb06  ldloc.0
0xb07  ldarg.1
0xb08  stfld    class [mscorlib]System.IServiceProvider <>c__DisplayClass0_0::serviceProvider
0xb0d  nop
0xb0e  ldloc.0
0xb0f  ldloc.0
0xb10  ldfld    class [mscorlib]System.IServiceProvider <>c__DisplayClass0_0::serviceProvider
0xb15  ldstr    aJsonconverterd// "JsonConverterDeletePlugin"
0xb1a  call     class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Bootstrapper::Bootstrap(class [mscorlib]System.IServiceProvider serviceProvider, string pluginName)
0xb1f  stfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass0_0::boot
0xb24  ldloc.0
0xb25  ldfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass0_0::boot
0xb2a  callvirt instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::get_LogContext()
0xb2f  callvirt instance class Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_ExecutionStatusLogger()
0xb34  ldstr    aDispatch// "Dispatch"
0xb39  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterDeletePluginActivityType>::get_Instance()
0xb3e  ldloc.0
0xb3f  ldftn    instance void <>c__DisplayClass0_0::<Execute>b__0()
0xb45  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0xb4a  callvirt instance void Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::Execute(string message, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType activityType, class [mscorlib]System.Action work)
0xb4f  nop
0xb50  ret
```
