# Microsoft.Crm.Sdk.Crm2007.Request::.ctor

- ea: `0xa990`
- end: `0xa9b1`
- name: `Microsoft.Crm.Sdk.Crm2007.Request::.ctor`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x8430`

## callees

- `0x16a0`
- `0x4590`

## string_xrefs

- `0xa991`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa990  ldarg.0
0xa991  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0xa996  call     instance void Microsoft.Crm.Sdk.RequestBase::.ctor(string typeNamespace)
0xa99b  ldarg.0
0xa99c  ldtoken  class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0xa9a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa9a6  newobj   instance void Microsoft.Crm.Sdk.ClrTypeParser::.ctor(class [mscorlib]System.Type type)
0xa9ab  stfld    class Microsoft.Crm.Sdk.ClrTypeParser Microsoft.Crm.Sdk.Crm2007.Request::_optionalParamsParser
0xa9b0  ret
```
