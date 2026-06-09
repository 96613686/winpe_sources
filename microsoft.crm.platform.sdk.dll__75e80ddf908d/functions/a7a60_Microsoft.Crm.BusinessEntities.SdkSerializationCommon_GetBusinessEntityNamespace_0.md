# Microsoft.Crm.BusinessEntities.SdkSerializationCommon::GetBusinessEntityNamespace_0

- ea: `0xa7a60`
- end: `0xa7a98`
- name: `Microsoft.Crm.BusinessEntities.SdkSerializationCommon::GetBusinessEntityNamespace_0`
- size: `56`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9dcd0`
- `0xa6ea0`
- `0xa6f60`
- `0xa7070`
- `0xa7a50`
- `0xa80f0`
- `0xa8140`
- `0xa82f0`
- `0xa83e0`
- `0xa8420`
- `0xa8490`

## callees

- `0xa7a60`

## string_xrefs

- `0xa7a61`: `http://schemas.microsoft.com/crm/2006/WebServices`
- `0xa7a87`: `http://schemas.microsoft.com/crm/2006/WebServices`
- `0xa7a6e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0xa7a7b`: `http://schemas.microsoft.com/crm/2009/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa7a60  ldarg.0
0xa7a61  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/crm/2006/W"...
0xa7a66  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa7a6b  brtrue.s loc_A7A87
0xa7a6d  ldarg.0
0xa7a6e  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/crm/2007/W"...
0xa7a73  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa7a78  brtrue.s loc_A7A87
0xa7a7a  ldarg.0
0xa7a7b  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2009/W"...
0xa7a80  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa7a85  brfalse.s loc_A7A8D
0xa7a87  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/crm/2006/W"...
0xa7a8c  ret
0xa7a8d  ldstr    aUnrecognizedEn// "Unrecognized entity collection namespac"...
0xa7a92  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0xa7a97  throw
```
