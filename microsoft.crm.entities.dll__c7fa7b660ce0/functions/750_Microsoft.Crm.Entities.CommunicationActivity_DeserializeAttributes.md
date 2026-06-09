# Microsoft.Crm.Entities.CommunicationActivity::DeserializeAttributes

- ea: `0x750`
- end: `0x793`
- name: `Microsoft.Crm.Entities.CommunicationActivity::DeserializeAttributes`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x100`
- `0x750`
- `0xc60`

## pseudocode

```c

```

## disassembly

```asm
0x750  ldarg.0
0x751  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x756  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x75b  stloc.0
0x75c  br.s     loc_76F
0x75e  ldloc.0
0x75f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x764  castclass Microsoft.Crm.Entities.PartyMappingItem
0x769  ldnull
0x76a  callvirt instance void Microsoft.Crm.Entities.PartyMappingItem::set_Parties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection value)
0x76f  ldloc.0
0x770  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x775  brtrue.s loc_75E
0x777  leave.s  loc_78A
0x779  ldloc.0
0x77a  isinst   [mscorlib]System.IDisposable
0x77f  stloc.1
0x780  ldloc.1
0x781  brfalse.s loc_789
0x783  ldloc.1
0x784  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x789  endfinally
0x78a  ldarg.0
0x78b  ldarg.1
0x78c  ldarg.2
0x78d  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::DeserializeAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityDeserializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntityDeserializationStrategy)
0x792  ret
```
