# Microsoft.Crm.Entities.SdkMessageRequest::ReadAttribute

- ea: `0x3b50`
- end: `0x3b81`
- name: `Microsoft.Crm.Entities.SdkMessageRequest::ReadAttribute`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3b50`

## pseudocode

```c

```

## disassembly

```asm
0x3b50  ldarg.3
0x3b51  ldstr    aSdkmessagerequ_2// "sdkmessagerequestfields"
0x3b56  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3b5b  brfalse.s loc_3B77
0x3b5d  ldarg.2
0x3b5e  ldarg.1
0x3b5f  ldstr    aSdkmessagerequ_1// "SdkMessageRequestField"
0x3b64  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy::ReadChildEntitiesCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, string)
0x3b69  stloc.0
0x3b6a  ldarg.0
0x3b6b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.SdkMessageRequest::_requestFields
0x3b70  ldloc.0
0x3b71  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::AddRange(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x3b76  ret
0x3b77  ldarg.0
0x3b78  ldarg.1
0x3b79  ldarg.2
0x3b7a  ldarg.3
0x3b7b  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ReadAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy, string)
0x3b80  ret
```
