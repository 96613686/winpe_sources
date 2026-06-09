# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin::.cctor

- ea: `0x11c0`
- end: `0x11dc`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin::.cctor`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x11ca`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x11c0  ldtoken  Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin
0x11c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11ca  ldstr    aUpdate// "Update"
0x11cf  ldc.i4.s 0x24
0x11d1  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x11d6  stsfld   class [mscorlib]System.Reflection.MethodInfo Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin::UpdateMethod
0x11db  ret
```
