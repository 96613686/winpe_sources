# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Bootstrapper::Bootstrap

- ea: `0x120`
- end: `0x165`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.Bootstrapper::Bootstrap`
- size: `69`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x800`
- `0xb00`
- `0xb80`
- `0xef0`
- `0x11f0`

## callees

- `0xb0`
- `0xd0`
- `0xf0`
- `0x100`
- `0x120`
- `0x290`

## pseudocode

```c

```

## disassembly

```asm
0x120  nop
0x121  ldarg.0
0x122  call     T0x2B000003
0x127  stloc.0
0x128  ldarg.0
0x129  call     T0x2B000004
0x12e  stloc.1
0x12f  ldarg.0
0x130  call     T0x2B000005
0x135  stloc.2
0x136  newobj   instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::.ctor()
0x13b  dup
0x13c  ldloc.0
0x13d  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::set_PluginContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext value)
0x142  nop
0x143  dup
0x144  ldloc.1
0x145  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::set_DataContext(class [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IDataProviderContext value)
0x14a  nop
0x14b  dup
0x14c  ldloc.2
0x14d  ldloc.1
0x14e  ldloc.0
0x14f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_MessageName()
0x154  ldarg.1
0x155  call     class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::Create(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILoggerFactory loggerFactory, class [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IDataProviderContext dataProviderContext, string sdkMessageName, string pluginName)
0x15a  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.BootstrapContext::set_LogContext(class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext value)
0x15f  nop
0x160  stloc.3
0x161  br.s     loc_163
0x163  ldloc.3
0x164  ret
```
