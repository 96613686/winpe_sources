# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::set_GlobalScopedLogger

- ea: `0x1c0`
- end: `0x1c8`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::set_GlobalScopedLogger`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x290`

## pseudocode

```c

```

## disassembly

```asm
0x1c0  ldarg.0
0x1c1  ldarg.1
0x1c2  stfld    class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger> Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::<GlobalScopedLogger>k__BackingField
0x1c7  ret
```
