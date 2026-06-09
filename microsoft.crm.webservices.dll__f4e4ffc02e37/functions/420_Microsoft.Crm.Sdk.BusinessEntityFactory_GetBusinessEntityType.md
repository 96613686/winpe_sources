# Microsoft.Crm.Sdk.BusinessEntityFactory::GetBusinessEntityType

- ea: `0x420`
- end: `0x475`
- name: `Microsoft.Crm.Sdk.BusinessEntityFactory::GetBusinessEntityType`
- size: `85`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x480`
- `0x1080`
- `0x1710`
- `0x77d0`
- `0x78f0`

## callees

- `0x420`

## string_xrefs

- `0x421`: `http://schemas.microsoft.com/crm/2006/WebServices`
- `0x42e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x43b`: `http://schemas.microsoft.com/crm/2009/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x420  ldarg.0
0x421  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0x426  call     bool [mscorlib]System.String::op_Equality(string, string)
0x42b  brtrue.s loc_449
0x42d  ldarg.0
0x42e  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x433  call     bool [mscorlib]System.String::op_Equality(string, string)
0x438  brtrue.s loc_454
0x43a  ldarg.0
0x43b  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/crm/2009/W"...
0x440  call     bool [mscorlib]System.String::op_Equality(string, string)
0x445  brtrue.s loc_45F
0x447  br.s     loc_46A
0x449  ldtoken  Microsoft.Crm.Sdk.Crm2006.BusinessEntity
0x44e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x453  ret
0x454  ldtoken  Microsoft.Crm.Sdk.Crm2007.BusinessEntity
0x459  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x45e  ret
0x45f  ldtoken  Microsoft.Crm.Sdk.Crm2009.BusinessEntity
0x464  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x469  ret
0x46a  ldstr    aUnrecognizedEn// "Unrecognized entity namespace."
0x46f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x474  throw
```
