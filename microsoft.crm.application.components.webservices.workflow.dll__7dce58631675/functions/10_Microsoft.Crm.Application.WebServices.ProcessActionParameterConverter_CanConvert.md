# Microsoft.Crm.Application.WebServices.ProcessActionParameterConverter::CanConvert

- ea: `0x10`
- end: `0x21`
- name: `Microsoft.Crm.Application.WebServices.ProcessActionParameterConverter::CanConvert`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldarg.1
0x11  ldtoken  class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x16  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20  ret
```
