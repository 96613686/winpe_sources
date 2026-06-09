# Microsoft.Crm.Entities.CommunicationActivity::.ctor

- ea: `0xd0`
- end: `0xf5`
- name: `Microsoft.Crm.Entities.CommunicationActivity::.ctor`
- size: `37`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xab0`
- `0xe10`
- `0xe60`

## callees

- `0x100`
- `0xbe0`
- `0xd40`
- `0xdf0`

## pseudocode

```c

```

## disassembly

```asm
0xd0  ldarg.0
0xd1  ldarg.1
0xd2  ldarg.2
0xd3  call     instance void Microsoft.Crm.Entities.GenericActivity::.ctor(string platformName, valuetype [mscorlib]System.Guid organizationId)
0xd8  ldarg.0
0xd9  newobj   instance void Microsoft.Crm.Entities.PartyMappingCollection::.ctor()
0xde  stfld    class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::partyMappingCollection
0xe3  ldarg.0
0xe4  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0xe9  ldc.i4.1
0xea  ldstr    aFrom// "from"
0xef  callvirt instance void Microsoft.Crm.Entities.PartyMappingCollection::AddMapping(valuetype Microsoft.Crm.Entities.ParticipationType type, string logicalName)
0xf4  ret
```
