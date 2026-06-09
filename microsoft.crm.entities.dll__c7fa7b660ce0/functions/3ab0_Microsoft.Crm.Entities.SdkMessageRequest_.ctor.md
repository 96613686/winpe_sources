# Microsoft.Crm.Entities.SdkMessageRequest::.ctor

- ea: `0x3ab0`
- end: `0x3ace`
- name: `Microsoft.Crm.Entities.SdkMessageRequest::.ctor`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x38c0`

## pseudocode

```c

```

## disassembly

```asm
0x3ab0  ldarg.0
0x3ab1  ldstr    aSdkmessagerequ_0// "SdkMessageRequest"
0x3ab6  ldarg.1
0x3ab7  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, valuetype [mscorlib]System.Guid)
0x3abc  ldarg.0
0x3abd  ldstr    aSdkmessagerequ_1// "SdkMessageRequestField"
0x3ac2  ldarg.1
0x3ac3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x3ac8  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.SdkMessageRequest::_requestFields
0x3acd  ret
```
