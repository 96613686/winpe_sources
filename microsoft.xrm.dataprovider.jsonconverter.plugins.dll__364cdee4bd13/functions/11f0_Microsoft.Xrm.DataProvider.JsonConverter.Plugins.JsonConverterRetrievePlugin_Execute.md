# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrievePlugin::Execute

- ea: `0x11f0`
- end: `0x126c`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrievePlugin::Execute`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xe0`
- `0x120`
- `0x190`
- `0x1b0`
- `0x1d0`
- `0x16b0`
- `0x2070`

## string_xrefs

- `0x120c`: `JsonConverterRetrievePlugin`

## pseudocode

```c

```

## disassembly

```asm
0x11f0  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x11f5  stloc.0
0x11f6  ldloc.0
0x11f7  ldarg.1
0x11f8  stfld    class [mscorlib]System.IServiceProvider <>c__DisplayClass1_0::serviceProvider
0x11fd  ldloc.0
0x11fe  ldarg.0
0x11ff  stfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrievePlugin <>c__DisplayClass1_0::<>4__this
0x1204  nop
0x1205  ldloc.0
0x1206  ldloc.0
0x1207  ldfld    class [mscorlib]System.IServiceProvider <>c__DisplayClass1_0::serviceProvider
0x120c  ldstr    aJsonconverterr_0// "JsonConverterRetrievePlugin"
0x1211  call     class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Bootstrapper::Bootstrap(class [mscorlib]System.IServiceProvider serviceProvider, string pluginName)
0x1216  stfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass1_0::boot
0x121b  ldloc.0
0x121c  ldfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass1_0::boot
0x1221  callvirt instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::get_LogContext()
0x1226  stloc.1
0x1227  ldloc.0
0x1228  ldloc.1
0x1229  callvirt instance class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger> Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_GlobalScopedLogger()
0x122e  stfld    class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger> <>c__DisplayClass1_0::globalScopedLogger
0x1233  ldloc.0
0x1234  ldloc.1
0x1235  callvirt instance class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_SdkMessageScopedLogger()
0x123a  stfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger <>c__DisplayClass1_0::sdkMessageScopedlogger
0x123f  ldloc.0
0x1240  ldfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass1_0::boot
0x1245  callvirt instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::get_LogContext()
0x124a  callvirt instance class Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_ExecutionStatusLogger()
0x124f  ldstr    aDispatch// "Dispatch"
0x1254  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterRetrievePluginActivityType>::get_Instance()
0x1259  ldloc.0
0x125a  ldftn    instance void <>c__DisplayClass1_0::<Execute>b__0()
0x1260  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1265  callvirt instance void Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::Execute(string message, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType activityType, class [mscorlib]System.Action work)
0x126a  nop
0x126b  ret
```
