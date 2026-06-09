# Microsoft.Crm.Entities.SdkMessageResponse::ReadAttribute

- ea: `0x3c70`
- end: `0x3ca1`
- name: `Microsoft.Crm.Entities.SdkMessageResponse::ReadAttribute`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3c70`

## pseudocode

```c

```

## disassembly

```asm
0x3c70  ldarg.3
0x3c71  ldstr    aSdkmessageresp_2// "sdkmessageresponsefields"
0x3c76  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3c7b  brfalse.s loc_3C97
0x3c7d  ldarg.2
0x3c7e  ldarg.1
0x3c7f  ldstr    aSdkmessageresp_1// "SdkMessageResponseField"
0x3c84  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy::ReadChildEntitiesCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, string)
0x3c89  stloc.0
0x3c8a  ldarg.0
0x3c8b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.SdkMessageResponse::_responseFields
0x3c90  ldloc.0
0x3c91  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::AddRange(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x3c96  ret
0x3c97  ldarg.0
0x3c98  ldarg.1
0x3c99  ldarg.2
0x3c9a  ldarg.3
0x3c9b  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ReadAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy, string)
0x3ca0  ret
```
