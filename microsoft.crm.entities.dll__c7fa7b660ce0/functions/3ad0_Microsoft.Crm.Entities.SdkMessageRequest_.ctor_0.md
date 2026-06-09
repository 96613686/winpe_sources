# Microsoft.Crm.Entities.SdkMessageRequest::.ctor_0

- ea: `0x3ad0`
- end: `0x3af3`
- name: `Microsoft.Crm.Entities.SdkMessageRequest::.ctor_0`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x38f0`

## pseudocode

```c

```

## disassembly

```asm
0x3ad0  ldarg.0
0x3ad1  ldstr    aSdkmessagerequ_0// "SdkMessageRequest"
0x3ad6  ldarg.1
0x3ad7  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3adc  ldarg.0
0x3add  ldstr    aSdkmessagerequ_1// "SdkMessageRequestField"
0x3ae2  ldarg.1
0x3ae3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3ae8  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x3aed  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.SdkMessageRequest::_requestFields
0x3af2  ret
```
