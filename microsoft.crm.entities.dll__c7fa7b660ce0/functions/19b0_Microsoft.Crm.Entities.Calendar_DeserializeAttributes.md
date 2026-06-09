# Microsoft.Crm.Entities.Calendar::DeserializeAttributes

- ea: `0x19b0`
- end: `0x19c4`
- name: `Microsoft.Crm.Entities.Calendar::DeserializeAttributes`
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
0x19b0  ldarg.0
0x19b1  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.Calendar::_calendarRules
0x19b6  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x19bb  ldarg.0
0x19bc  ldarg.1
0x19bd  ldarg.2
0x19be  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::DeserializeAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy)
0x19c3  ret
```
