# Microsoft.Crm.Entities.CommunicationActivity::ReadAttribute

- ea: `0x7a0`
- end: `0x7f2`
- name: `Microsoft.Crm.Entities.CommunicationActivity::ReadAttribute`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x100`
- `0x7a0`
- `0xc50`
- `0xc60`
- `0xdb0`

## pseudocode

```c

```

## disassembly

```asm
0x7a0  ldarg.0
0x7a1  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x7a6  ldarg.3
0x7a7  callvirt instance class Microsoft.Crm.Entities.PartyMappingItem Microsoft.Crm.Entities.PartyMappingCollection::Find(string logicalName)
0x7ac  stloc.0
0x7ad  ldloc.0
0x7ae  brfalse.s loc_7E8
0x7b0  ldloc.0
0x7b1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x7b6  brtrue.s loc_7CE
0x7b8  ldloc.0
0x7b9  ldstr    aActivityparty// "ActivityParty"
0x7be  ldarg.0
0x7bf  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_OrganizationId()
0x7c4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x7c9  callvirt instance void Microsoft.Crm.Entities.PartyMappingItem::set_Parties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection value)
0x7ce  ldarg.2
0x7cf  ldarg.1
0x7d0  ldstr    aActivityparty// "ActivityParty"
0x7d5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy::ReadChildEntitiesCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, string)
0x7da  stloc.1
0x7db  ldloc.0
0x7dc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x7e1  ldloc.1
0x7e2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::AddRange(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x7e7  ret
0x7e8  ldarg.0
0x7e9  ldarg.1
0x7ea  ldarg.2
0x7eb  ldarg.3
0x7ec  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ReadAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy, string)
0x7f1  ret
```
