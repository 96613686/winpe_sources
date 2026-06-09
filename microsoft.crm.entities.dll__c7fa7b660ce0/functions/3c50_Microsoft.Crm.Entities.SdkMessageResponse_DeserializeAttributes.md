# Microsoft.Crm.Entities.SdkMessageResponse::DeserializeAttributes

- ea: `0x3c50`
- end: `0x3c64`
- name: `Microsoft.Crm.Entities.SdkMessageResponse::DeserializeAttributes`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x3c50  ldarg.0
0x3c51  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.SdkMessageResponse::_responseFields
0x3c56  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x3c5b  ldarg.0
0x3c5c  ldarg.1
0x3c5d  ldarg.2
0x3c5e  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::DeserializeAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy)
0x3c63  ret
```
