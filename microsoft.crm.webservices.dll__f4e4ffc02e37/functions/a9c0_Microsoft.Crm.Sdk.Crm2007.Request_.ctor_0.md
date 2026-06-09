# Microsoft.Crm.Sdk.Crm2007.Request::.ctor_0

- ea: `0xa9c0`
- end: `0xa9e4`
- name: `Microsoft.Crm.Sdk.Crm2007.Request::.ctor_0`
- size: `36`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3200`
- `0x3b10`
- `0x3b60`
- `0x3c20`
- `0x40b0`

## callees

- `0x16a0`
- `0x45a0`

## string_xrefs

- `0xa9c1`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa9c0  ldarg.0
0xa9c1  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0xa9c6  ldarg.1
0xa9c7  ldarg.2
0xa9c8  ldarg.3
0xa9c9  call     instance void Microsoft.Crm.Sdk.RequestBase::.ctor(string typeNamespace, string requestName, bool returnDynamicEntities, valuetype [mscorlib]System.Guid organizationId)
0xa9ce  ldarg.0
0xa9cf  ldtoken  class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0xa9d4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa9d9  newobj   instance void Microsoft.Crm.Sdk.ClrTypeParser::.ctor(class [mscorlib]System.Type type)
0xa9de  stfld    class Microsoft.Crm.Sdk.ClrTypeParser Microsoft.Crm.Sdk.Crm2007.Request::_optionalParamsParser
0xa9e3  ret
```
