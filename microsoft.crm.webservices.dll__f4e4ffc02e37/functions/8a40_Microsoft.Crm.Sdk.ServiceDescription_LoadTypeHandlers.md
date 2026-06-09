# Microsoft.Crm.Sdk.ServiceDescription::LoadTypeHandlers

- ea: `0x8a40`
- end: `0x8a5d`
- name: `Microsoft.Crm.Sdk.ServiceDescription::LoadTypeHandlers`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x88e0`

## callees

- `0x8a60`
- `0x8ae0`

## pseudocode

```c

```

## disassembly

```asm
0x8a40  ldarg.0
0x8a41  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadTypeParsers()
0x8a46  ldarg.0
0x8a47  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConverterFactory [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConverterFactory::get_Instance()
0x8a4c  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.IConverter> [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConverterFactory::get_InternalDictionary()
0x8a51  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.IConverter> Microsoft.Crm.Sdk.ServiceDescription::_converters
0x8a56  ldarg.0
0x8a57  call     instance void Microsoft.Crm.Sdk.ServiceDescription::LoadTypeFormatters()
0x8a5c  ret
```
