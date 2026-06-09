# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::Execute

- ea: `0xb80`
- end: `0xbfc`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::Execute`
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
- `0x1ed0`

## string_xrefs

- `0xb9c`: `JsonConverterRetrieveMultiplePlugin`

## pseudocode

```c

```

## disassembly

```asm
0xb80  newobj   instance void <>c__DisplayClass1_0::.ctor()
0xb85  stloc.0
0xb86  ldloc.0
0xb87  ldarg.1
0xb88  stfld    class [mscorlib]System.IServiceProvider <>c__DisplayClass1_0::serviceProvider
0xb8d  ldloc.0
0xb8e  ldarg.0
0xb8f  stfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin <>c__DisplayClass1_0::<>4__this
0xb94  nop
0xb95  ldloc.0
0xb96  ldloc.0
0xb97  ldfld    class [mscorlib]System.IServiceProvider <>c__DisplayClass1_0::serviceProvider
0xb9c  ldstr    aJsonconverterr// "JsonConverterRetrieveMultiplePlugin"
0xba1  call     class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Bootstrapper::Bootstrap(class [mscorlib]System.IServiceProvider serviceProvider, string pluginName)
0xba6  stfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass1_0::boot
0xbab  ldloc.0
0xbac  ldfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass1_0::boot
0xbb1  callvirt instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::get_LogContext()
0xbb6  stloc.1
0xbb7  ldloc.0
0xbb8  ldloc.1
0xbb9  callvirt instance class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger> Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_GlobalScopedLogger()
0xbbe  stfld    class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger> <>c__DisplayClass1_0::globalScopedLazyLogger
0xbc3  ldloc.0
0xbc4  ldloc.1
0xbc5  callvirt instance class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_SdkMessageScopedLogger()
0xbca  stfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger <>c__DisplayClass1_0::sdkMessageScopedlogger
0xbcf  ldloc.0
0xbd0  ldfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass1_0::boot
0xbd5  callvirt instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::get_LogContext()
0xbda  callvirt instance class Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_ExecutionStatusLogger()
0xbdf  ldstr    aDispatch// "Dispatch"
0xbe4  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterRetrieveMultiplePluginActivityType>::get_Instance()
0xbe9  ldloc.0
0xbea  ldftn    instance void <>c__DisplayClass1_0::<Execute>b__0()
0xbf0  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0xbf5  callvirt instance void Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::Execute(string message, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType activityType, class [mscorlib]System.Action work)
0xbfa  nop
0xbfb  ret
```
