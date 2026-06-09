# Microsoft.Crm.Entities.SdkMessageResponse::.ctor

- ea: `0x3bd0`
- end: `0x3bee`
- name: `Microsoft.Crm.Entities.SdkMessageResponse::.ctor`
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
0x3bd0  ldarg.0
0x3bd1  ldstr    aSdkmessageresp_0// "SdkMessageResponse"
0x3bd6  ldarg.1
0x3bd7  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, valuetype [mscorlib]System.Guid)
0x3bdc  ldarg.0
0x3bdd  ldstr    aSdkmessageresp_1// "SdkMessageResponseField"
0x3be2  ldarg.1
0x3be3  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x3be8  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.SdkMessageResponse::_responseFields
0x3bed  ret
```
