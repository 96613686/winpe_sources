# Microsoft.Crm.Entities.ServiceAppointment::.ctor

- ea: `0xe60`
- end: `0xe91`
- name: `Microsoft.Crm.Entities.ServiceAppointment::.ctor`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xd0`
- `0x100`
- `0xd40`

## string_xrefs

- `0xe61`: `ServiceAppointment`

## pseudocode

```c

```

## disassembly

```asm
0xe60  ldarg.0
0xe61  ldstr    aServiceappoint// "ServiceAppointment"
0xe66  ldarg.1
0xe67  call     instance void Microsoft.Crm.Entities.CommunicationActivity::.ctor(string platformName, valuetype [mscorlib]System.Guid organizationId)
0xe6c  ldarg.0
0xe6d  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0xe72  ldc.i4.s 0xA
0xe74  ldstr    aResources// "resources"
0xe79  callvirt instance void Microsoft.Crm.Entities.PartyMappingCollection::AddMapping(valuetype Microsoft.Crm.Entities.ParticipationType type, string logicalName)
0xe7e  ldarg.0
0xe7f  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0xe84  ldc.i4.s 0xB
0xe86  ldstr    aCustomers// "customers"
0xe8b  callvirt instance void Microsoft.Crm.Entities.PartyMappingCollection::AddMapping(valuetype Microsoft.Crm.Entities.ParticipationType type, string logicalName)
0xe90  ret
```
