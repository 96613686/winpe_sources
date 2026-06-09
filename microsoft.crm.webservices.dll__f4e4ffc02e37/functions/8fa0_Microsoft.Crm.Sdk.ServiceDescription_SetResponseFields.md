# Microsoft.Crm.Sdk.ServiceDescription::SetResponseFields

- ea: `0x8fa0`
- end: `0x8fc1`
- name: `Microsoft.Crm.Sdk.ServiceDescription::SetResponseFields`
- size: `33`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x8bf0`
- `0x8e90`
- `0x8fd0`

## callees

- `0x65a0`
- `0x66a0`
- `0x91c0`

## pseudocode

```c

```

## disassembly

```asm
0x8fa0  ldarg.0
0x8fa1  ldarg.1
0x8fa2  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageResponseType Microsoft.Crm.Sdk.ResponseDescription::get_Response()
0x8fa7  ldarg.0
0x8fa8  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.IConverter> Microsoft.Crm.Sdk.ServiceDescription::_converters
0x8fad  ldarg.0
0x8fae  ldfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_fieldFormatters
0x8fb3  call     instance class Microsoft.Crm.Sdk.ResponseFieldDescription[] Microsoft.Crm.Sdk.ServiceDescription::LoadResponseFields(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageResponseType response, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.IConverter> converters, class [mscorlib]System.Collections.IDictionary fieldFormatters)
0x8fb8  stloc.0
0x8fb9  ldarg.1
0x8fba  ldloc.0
0x8fbb  callvirt instance void Microsoft.Crm.Sdk.ResponseDescription::set_Fields(class Microsoft.Crm.Sdk.ResponseFieldDescription[] value)
0x8fc0  ret
```
