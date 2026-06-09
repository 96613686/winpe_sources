# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::Create

- ea: `0x290`
- end: `0x3c1`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::Create`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x120`

## callees

- `0x1a0`
- `0x1c0`
- `0x1e0`
- `0x200`
- `0x220`
- `0x260`
- `0x270`
- `0x290`
- `0x3d0`
- `0x1690`
- `0x1bb0`

## string_xrefs

- `0x2d2`: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins`
- `0x2de`: `pluginName`

## pseudocode

```c

```

## disassembly

```asm
0x290  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x295  stloc.0
0x296  nop
0x297  ldloc.0
0x298  ldarg.0
0x299  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x29e  dup
0x29f  ldstr    aDatasource// "datasource"
0x2a4  ldarg.1
0x2a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IDataProviderContext::get_DataSourceId()
0x2aa  box      [mscorlib]System.Guid
0x2af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2b4  nop
0x2b5  dup
0x2b6  ldstr    aDataprovider// "dataprovider"
0x2bb  ldarg.1
0x2bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IDataProviderContext::get_DataProviderId()
0x2c1  box      [mscorlib]System.Guid
0x2c6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2cb  nop
0x2cc  dup
0x2cd  ldstr    aAssemblyname// "assemblyName"
0x2d2  ldstr    aMicrosoftXrmDa// "Microsoft.Xrm.DataProvider.JsonConverte"...
0x2d7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2dc  nop
0x2dd  dup
0x2de  ldstr    aPluginname// "pluginName"
0x2e3  ldarg.3
0x2e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2e9  nop
0x2ea  dup
0x2eb  ldstr    aSdkmessage// "sdkMessage"
0x2f0  ldarg.2
0x2f1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2f6  nop
0x2f7  dup
0x2f8  ldstr    aPrimaryentitym// "primaryEntityMetadataId"
0x2fd  ldarg.1
0x2fe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IDataProviderContext::get_PrimaryEntityMetadataId()
0x303  box      [mscorlib]System.Guid
0x308  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x30d  nop
0x30e  dup
0x30f  ldstr    aVersion// "version"
0x314  ldsfld   string Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::DataProviderVersion
0x319  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x31e  nop
0x31f  callvirt instance class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILoggerFactory [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILoggerFactory::CreateContext(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x324  stfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILoggerFactory <>c__DisplayClass5_0::sdkMessageScopeContext
0x329  ldloc.0
0x32a  ldftn    instance class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger <>c__DisplayClass5_0::<Create>b__0()
0x330  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger>::.ctor(object, native int)
0x335  newobj   instance void class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x33a  stloc.1
0x33b  ldloc.0
0x33c  ldfld    class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILoggerFactory <>c__DisplayClass5_0::sdkMessageScopeContext
0x341  ldstr    aMicrosoftXrmDa_0// "Microsoft.Xrm.DataProvider"
0x346  callvirt instance class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILoggerFactory::GetLogger(string)
0x34b  stloc.2
0x34c  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0x351  ldtoken  Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory
0x356  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x35b  callvirt instance string [mscorlib]System.Type::get_Namespace()
0x360  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0x365  stloc.3
0x366  ldloc.2
0x367  ldloc.3
0x368  ldsfld   class Microsoft.Xrm.DataProvider.Logger.IExceptionAnalyzer Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::ExceptionAnalyzer
0x36d  newobj   instance void Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger::.ctor(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger executionlogger, class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger xrmLogger, class Microsoft.Xrm.DataProvider.Logger.IExceptionAnalyzer exceptionAnalyzer)
0x372  stloc.s  4
0x374  ldloc.2
0x375  newobj   instance void [Microsoft.Xrm.Log]Microsoft.Xrm.Log.PerformanceContextFactory::.ctor(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger)
0x37a  stloc.s  5
0x37c  newobj   instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::.ctor()
0x381  dup
0x382  ldloc.2
0x383  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::set_SdkMessageScopedLogger(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger value)
0x388  nop
0x389  dup
0x38a  ldloc.1
0x38b  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::set_GlobalScopedLogger(class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger> value)
0x390  nop
0x391  dup
0x392  ldloc.s  4
0x394  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::set_ExecutionStatusLogger(class Microsoft.Xrm.DataProvider.Logger.ExecutionStatusLogger value)
0x399  nop
0x39a  dup
0x39b  ldloc.3
0x39c  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::set_XrmLogger(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger value)
0x3a1  nop
0x3a2  dup
0x3a3  ldloc.s  5
0x3a5  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::set_PerformanceContextFactory(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.PerformanceContextFactory value)
0x3aa  nop
0x3ab  dup
0x3ac  ldarg.1
0x3ad  ldarg.2
0x3ae  ldarg.3
0x3af  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::GetCustomPropertiesToActivity(class [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IDataProviderContext dataProviderContext, string sdkMessageName, string pluginName)
0x3b4  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::set_ActivityCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> value)
0x3b9  nop
0x3ba  stloc.s  6
0x3bc  br.s     loc_3BE
0x3be  ldloc.s  6
0x3c0  ret
```
