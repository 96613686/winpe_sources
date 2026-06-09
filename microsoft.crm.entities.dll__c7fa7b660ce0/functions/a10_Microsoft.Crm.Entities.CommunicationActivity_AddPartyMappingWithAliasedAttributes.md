# Microsoft.Crm.Entities.CommunicationActivity::AddPartyMappingWithAliasedAttributes

- ea: `0xa10`
- end: `0xa37`
- name: `Microsoft.Crm.Entities.CommunicationActivity::AddPartyMappingWithAliasedAttributes`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xab0`

## callees

- `0x100`
- `0xd60`

## pseudocode

```c

```

## disassembly

```asm
0xa10  ldarg.3
0xa11  ldarg.0
0xa12  ldftn    instance bool Microsoft.Crm.Entities.CommunicationActivity::<AddPartyMappingWithAliasedAttributes>b__23_0(string attrAliasLogicalName)
0xa18  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xa1d  call     T0x2B000001
0xa22  stloc.0
0xa23  ldarg.0
0xa24  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0xa29  ldarg.1
0xa2a  ldarg.2
0xa2b  ldloc.0
0xa2c  call     T0x2B000002
0xa31  callvirt instance void Microsoft.Crm.Entities.PartyMappingCollection::AddMapping(valuetype Microsoft.Crm.Entities.ParticipationType type, string logicalName, string[] aliasedLogicalNames)
0xa36  ret
```
