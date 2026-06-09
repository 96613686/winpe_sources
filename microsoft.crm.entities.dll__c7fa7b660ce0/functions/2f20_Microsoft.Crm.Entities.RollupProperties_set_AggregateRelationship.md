# Microsoft.Crm.Entities.RollupProperties::set_AggregateRelationship

- ea: `0x2f20`
- end: `0x2f52`
- name: `Microsoft.Crm.Entities.RollupProperties::set_AggregateRelationship`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2f20`

## pseudocode

```c

```

## disassembly

```asm
0x2f20  ldarg.0
0x2f21  ldarg.1
0x2f22  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Entities.RollupProperties::_aggregateRelationship
0x2f27  ldarg.1
0x2f28  brfalse.s loc_2F41
0x2f2a  ldarg.0
0x2f2b  ldstr    aAggregaterelat// "aggregaterelationshipname"
0x2f30  ldarg.0
0x2f31  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship Microsoft.Crm.Entities.RollupProperties::_aggregateRelationship
0x2f36  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_Name()
0x2f3b  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f40  ret
0x2f41  ldarg.0
0x2f42  ldstr    aAggregaterelat// "aggregaterelationshipname"
0x2f47  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x2f4c  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2f51  ret
```
