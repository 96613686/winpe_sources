# Microsoft.Crm.Entities.RecipientEnabledActivity::.ctor

- ea: `0xe10`
- end: `0xe2a`
- name: `Microsoft.Crm.Entities.RecipientEnabledActivity::.ctor`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x30`

## callees

- `0xd0`
- `0x100`
- `0xd40`

## pseudocode

```c

```

## disassembly

```asm
0xe10  ldarg.0
0xe11  ldarg.1
0xe12  ldarg.2
0xe13  call     instance void Microsoft.Crm.Entities.CommunicationActivity::.ctor(string platformName, valuetype [mscorlib]System.Guid organizationId)
0xe18  ldarg.0
0xe19  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0xe1e  ldc.i4.2
0xe1f  ldstr    aTo// "to"
0xe24  callvirt instance void Microsoft.Crm.Entities.PartyMappingCollection::AddMapping(valuetype Microsoft.Crm.Entities.ParticipationType type, string logicalName)
0xe29  ret
```
