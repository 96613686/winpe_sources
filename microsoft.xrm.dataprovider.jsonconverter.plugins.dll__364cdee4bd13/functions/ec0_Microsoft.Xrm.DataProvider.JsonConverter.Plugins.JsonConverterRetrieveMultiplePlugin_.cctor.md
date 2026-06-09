# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::.cctor

- ea: `0xec0`
- end: `0xedc`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::.cctor`
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
0xec0  ldtoken  Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin
0xec5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xeca  ldstr    aRetrievemultip// "RetrieveMultiple"
0xecf  ldc.i4.s 0x24
0xed1  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0xed6  stsfld   class [mscorlib]System.Reflection.MethodInfo Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::RetrieveMultipleMethod
0xedb  ret
```
