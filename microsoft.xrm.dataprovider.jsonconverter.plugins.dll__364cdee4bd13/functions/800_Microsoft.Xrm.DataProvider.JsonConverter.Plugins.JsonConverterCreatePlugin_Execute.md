# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterCreatePlugin::Execute

- ea: `0x800`
- end: `0x87c`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterCreatePlugin::Execute`
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
- `0x1d50`

## string_xrefs

- `0x81c`: `JsonConverterCreatePlugin`

## pseudocode

```c

```

## disassembly

```asm
0x800  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x805  stloc.0
0x806  ldloc.0
0x807  ldarg.1
0x808  stfld    class [mscorlib]System.IServiceProvider <>c__DisplayClass1_0::serviceProvider
0x80d  ldloc.0
0x80e  ldarg.0
0x80f  stfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterCreatePlugin <>c__DisplayClass1_0::<>4__this
0x814  nop
0x815  ldloc.0
0x816  ldloc.0
0x817  ldfld    class [mscorlib]System.IServiceProvider <>c__DisplayClass1_0::serviceProvider
0x81c  ldstr    aJsonconverterc// "JsonConverterCreatePlugin"
0x821  call     class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Bootstrapper::Bootstrap(class [mscorlib]System.IServiceProvider serviceProvider, string pluginName)
0x826  stfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass1_0::boot
0x82b  ldloc.0
0x82c  ldfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass1_0::boot
0x831  callvirt instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::get_LogContext()
0x836  stloc.1
0x837  ldloc.0
0x838  ldloc.1
0x839  callvirt instance class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger> Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_GlobalScopedLogger()
0x83e  stfld    class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger> <>c__DisplayClass1_0::globalScopedLogger
0x843  ldloc.0
0x844  ldloc.1
0x845  callvirt instance class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_SdkMessageScopedLogger()
0x84a  stfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger <>c__DisplayClass1_0::sdkMessageScopedlogger
0x84f  ldloc.0
0x850  ldfld    class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext <>c__DisplayClass1_0::boot
0x855  callvirt instance class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::get_LogContext()
0x85a  callvirt instance class Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_ExecutionStatusLogger()
0x85f  ldstr    aDispatch// "Dispatch"
0x864  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Xrm.DataProvider.Logger.ActivityTypes.JsonConverterCreatePluginActivityType>::get_Instance()
0x869  ldloc.0
0x86a  ldftn    instance void <>c__DisplayClass1_0::<Execute>b__0()
0x870  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x875  callvirt instance void Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::Execute(string message, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType activityType, class [mscorlib]System.Action work)
0x87a  nop
0x87b  ret
```
