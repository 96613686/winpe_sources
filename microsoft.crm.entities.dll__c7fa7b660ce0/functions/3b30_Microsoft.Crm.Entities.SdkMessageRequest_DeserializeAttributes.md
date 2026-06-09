# Microsoft.Crm.Entities.SdkMessageRequest::DeserializeAttributes

- ea: `0x3b30`
- end: `0x3b44`
- name: `Microsoft.Crm.Entities.SdkMessageRequest::DeserializeAttributes`
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
0x3b30  ldarg.0
0x3b31  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.SdkMessageRequest::_requestFields
0x3b36  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x3b3b  ldarg.0
0x3b3c  ldarg.1
0x3b3d  ldarg.2
0x3b3e  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::DeserializeAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy)
0x3b43  ret
```
