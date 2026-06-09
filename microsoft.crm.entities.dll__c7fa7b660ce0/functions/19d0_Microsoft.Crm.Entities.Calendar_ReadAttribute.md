# Microsoft.Crm.Entities.Calendar::ReadAttribute

- ea: `0x19d0`
- end: `0x1a01`
- name: `Microsoft.Crm.Entities.Calendar::ReadAttribute`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x19d0`

## pseudocode

```c

```

## disassembly

```asm
0x19d0  ldarg.3
0x19d1  ldstr    aCalendarrules// "calendarrules"
0x19d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19db  brfalse.s loc_19F7
0x19dd  ldarg.2
0x19de  ldarg.1
0x19df  ldstr    aCalendarrule// "CalendarRule"
0x19e4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy::ReadChildEntitiesCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, string)
0x19e9  stloc.0
0x19ea  ldarg.0
0x19eb  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.Calendar::_calendarRules
0x19f0  ldloc.0
0x19f1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::AddRange(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x19f6  ret
0x19f7  ldarg.0
0x19f8  ldarg.1
0x19f9  ldarg.2
0x19fa  ldarg.3
0x19fb  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ReadAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy, string)
0x1a00  ret
```
