# Microsoft.Crm.Entities.CommunicationActivity::SerializeAttributes

- ea: `0x6f0`
- end: `0x749`
- name: `Microsoft.Crm.Entities.CommunicationActivity::SerializeAttributes`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x100`
- `0x6f0`
- `0xc50`
- `0xca0`

## pseudocode

```c

```

## disassembly

```asm
0x6f0  ldarg.0
0x6f1  ldarg.1
0x6f2  ldarg.2
0x6f3  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SerializeAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntitySerializationStrategy)
0x6f8  ldarg.0
0x6f9  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x6fe  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x703  stloc.0
0x704  br.s     loc_72D
0x706  ldloc.0
0x707  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x70c  castclass Microsoft.Crm.Entities.PartyMappingItem
0x711  stloc.1
0x712  ldloc.1
0x713  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x718  brfalse.s loc_72D
0x71a  ldarg.2
0x71b  ldarg.1
0x71c  ldloc.1
0x71d  callvirt instance string Microsoft.Crm.Entities.PartyMappingItem::get_LogicalName()
0x722  ldloc.1
0x723  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x728  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntitySerializationStrategy::WriteChildEntitiesCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext, string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x72d  ldloc.0
0x72e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x733  brtrue.s loc_706
0x735  leave.s  loc_748
0x737  ldloc.0
0x738  isinst   [mscorlib]System.IDisposable
0x73d  stloc.2
0x73e  ldloc.2
0x73f  brfalse.s loc_747
0x741  ldloc.2
0x742  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x747  endfinally
0x748  ret
```
