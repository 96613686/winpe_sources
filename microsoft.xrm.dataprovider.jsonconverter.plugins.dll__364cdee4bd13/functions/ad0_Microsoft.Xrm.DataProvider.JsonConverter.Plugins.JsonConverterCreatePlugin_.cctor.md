# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterCreatePlugin::.cctor

- ea: `0xad0`
- end: `0xaec`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterCreatePlugin::.cctor`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## string_xrefs

- `0xada`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0xad0  ldtoken  Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterCreatePlugin
0xad5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xada  ldstr    aCreate// "Create"
0xadf  ldc.i4.s 0x24
0xae1  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xae6  stsfld   class [mscorlib]System.Reflection.MethodInfo Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterCreatePlugin::CreateMethod
0xaeb  ret
```
