# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_GlobalScopedLogger

- ea: `0x1b0`
- end: `0x1b7`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::get_GlobalScopedLogger`
- size: `7`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x800`
- `0xb80`
- `0xef0`
- `0x11f0`

## pseudocode

```c

```

## disassembly

```asm
0x1b0  ldarg.0
0x1b1  ldfld    class [mscorlib]System.Lazy`1<class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger> Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContext::<GlobalScopedLogger>k__BackingField
0x1b6  ret
```
