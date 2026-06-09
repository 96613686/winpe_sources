# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JSonExceptionAnalyzer::.ctor

- ea: `0x70`
- end: `0x83`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JSonExceptionAnalyzer::.ctor`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x490`

## callees

- `0x19f0`

## pseudocode

```c

```

## disassembly

```asm
0x70  ldarg.0
0x71  newobj   instance void Microsoft.Xrm.DataProvider.Logger.DefaultExceptionAnalyzer::.ctor()
0x76  stfld    class Microsoft.Xrm.DataProvider.Logger.DefaultExceptionAnalyzer Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JSonExceptionAnalyzer::defaultExceptionAnalyzer
0x7b  ldarg.0
0x7c  call     instance void [mscorlib]System.Object::.ctor()
0x81  nop
0x82  ret
```
