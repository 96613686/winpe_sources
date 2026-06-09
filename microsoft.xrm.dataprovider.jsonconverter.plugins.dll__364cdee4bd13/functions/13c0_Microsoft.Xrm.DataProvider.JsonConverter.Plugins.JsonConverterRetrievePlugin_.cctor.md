# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrievePlugin::.cctor

- ea: `0x13c0`
- end: `0x13dc`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrievePlugin::.cctor`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x13c0  ldtoken  Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrievePlugin
0x13c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x13ca  ldstr    aRetrieve// "Retrieve"
0x13cf  ldc.i4.s 0x24
0x13d1  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x13d6  stsfld   class [mscorlib]System.Reflection.MethodInfo Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrievePlugin::RetrieveMethod
0x13db  ret
```
