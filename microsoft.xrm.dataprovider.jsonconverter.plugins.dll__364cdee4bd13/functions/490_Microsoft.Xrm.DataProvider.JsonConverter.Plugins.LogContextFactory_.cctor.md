# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::.cctor

- ea: `0x490`
- end: `0x4a5`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::.cctor`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x70`

## pseudocode

```c

```

## disassembly

```asm
0x490  newobj   instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JSonExceptionAnalyzer::.ctor()
0x495  stsfld   class Microsoft.Xrm.DataProvider.Logger.IExceptionAnalyzer Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::ExceptionAnalyzer
0x49a  ldstr    a90082// "9.0.0.82"
0x49f  stsfld   string Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::DataProviderVersion
0x4a4  ret
```
