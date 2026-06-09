# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin::Execute

- ea: `0xef0`
- end: `0xf6c`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin::Execute`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0xe0`
- `0x120`
- `0x190`
- `0x1b0`
- `0x1d0`
- `0x16b0`
- `0x1fb0`

## string_xrefs

- `0xf0c`: `JsonConverterUpdatePlugin`

## pseudocode

```c

```

## disassembly

```asm
0xef0  newobj   instance void <>c__DisplayClass2_0::.ctor()
0xef5  stloc.0
0xef6  ldloc.0
0xef7  ldarg.1
0xef8  stfld    class [mscorlib]System.IServiceProvider <>c__DisplayClass2_0::serviceProvider
0xefd  ldloc.0
0xefe  ldarg.0
0xeff  stfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin <>c__DisplayClass2_0::<>4__this
0xf04  nop
0xf05  ldloc.0
0xf06  ldloc.0
0xf07  ldfld    class [mscorlib]System.IServiceProvider <>c__DisplayClass2_0::serviceProvider
0xf0c  ldstr    aJsonconverteru// "JsonConverterUpdatePlugin"
0xf11  call     class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Bootstrapper::Bootstrap(class [mscorlib]System.IServiceProvider serviceProvider, string pluginName)
0xf16  stfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass2_0::boot
0xf1b  ldloc.0
0xf1c  ldfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass2_0::boot
0xf21  callvirt instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::get_LogContext()
0xf26  stloc.1
0xf27  ldloc.0
0xf28  ldloc.1
0xf29  callvirt instance class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger> Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_GlobalScopedLogger()
0xf2e  stfld    class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger> <>c__DisplayClass2_0::globalScopedLogger
0xf33  ldloc.0
0xf34  ldloc.1
0xf35  callvirt instance class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_SdkMessageScopedLogger()
0xf3a  stfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger <>c__DisplayClass2_0::sdkMessageScopedlogger
0xf3f  ldloc.0
0xf40  ldfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass2_0::boot
0xf45  callvirt instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::get_LogContext()
0xf4a  callvirt instance class Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_ExecutionStatusLogger()
0xf4f  ldstr    aDispatch// "Dispatch"
0xf54  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterRetrievePluginActivityType>::get_Instance()
0xf59  ldloc.0
0xf5a  ldftn    instance void <>c__DisplayClass2_0::<Execute>b__0()
0xf60  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0xf65  callvirt instance void Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::Execute(string message, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType activityType, class [mscorlib]System.Action work)
0xf6a  nop
0xf6b  ret
```
