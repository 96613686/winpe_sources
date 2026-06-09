# Microsoft.Crm.Sdk.BusinessEntityCollectionFactory::GetBusinessEntityCollectionType

- ea: `0x4b0`
- end: `0x505`
- name: `Microsoft.Crm.Sdk.BusinessEntityCollectionFactory::GetBusinessEntityCollectionType`
- size: `85`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x510`
- `0x1170`
- `0x17f0`

## callees

- `0x4b0`

## string_xrefs

- `0x4b1`: `http://schemas.microsoft.com/crm/2006/WebServices`
- `0x4be`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4cb`: `http://schemas.microsoft.com/crm/2009/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x4b0  ldarg.0
0x4b1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0x4b6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4bb  brtrue.s loc_4D9
0x4bd  ldarg.0
0x4be  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0x4c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4c8  brtrue.s loc_4E4
0x4ca  ldarg.0
0x4cb  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/crm/2009/W"...
0x4d0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4d5  brtrue.s loc_4EF
0x4d7  br.s     loc_4FA
0x4d9  ldtoken  Microsoft.Crm.Sdk.Crm2006.BusinessEntityCollection
0x4de  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e3  ret
0x4e4  ldtoken  Microsoft.Crm.Sdk.Crm2007.BusinessEntityCollection
0x4e9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ee  ret
0x4ef  ldtoken  Microsoft.Crm.Sdk.Crm2009.BusinessEntityCollection
0x4f4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f9  ret
0x4fa  ldstr    aUnrecognizedEn_0// "Unrecognized entity collection namespac"...
0x4ff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x504  throw
```
