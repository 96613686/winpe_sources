# Microsoft.Crm.Entities.CustomActivity::.ctor

- ea: `0xab0`
- end: `0xb67`
- name: `Microsoft.Crm.Entities.CustomActivity::.ctor`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xd0`
- `0x100`
- `0xa10`
- `0xd40`

## pseudocode

```c

```

## disassembly

```asm
0xab0  ldarg.0
0xab1  ldarg.1
0xab2  ldarg.2
0xab3  call     instance void Microsoft.Crm.Entities.CommunicationActivity::.ctor(string platformName, valuetype [mscorlib]System.Guid organizationId)
0xab8  ldarg.0
0xab9  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0xabe  ldc.i4.2
0xabf  ldstr    aTo// "to"
0xac4  callvirt instance void Microsoft.Crm.Entities.PartyMappingCollection::AddMapping(valuetype Microsoft.Crm.Entities.ParticipationType type, string logicalName)
0xac9  ldarg.0
0xaca  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0xacf  ldc.i4.3
0xad0  ldstr    aCc// "cc"
0xad5  callvirt instance void Microsoft.Crm.Entities.PartyMappingCollection::AddMapping(valuetype Microsoft.Crm.Entities.ParticipationType type, string logicalName)
0xada  ldarg.0
0xadb  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0xae0  ldc.i4.4
0xae1  ldstr    aBcc// "bcc"
0xae6  callvirt instance void Microsoft.Crm.Entities.PartyMappingCollection::AddMapping(valuetype Microsoft.Crm.Entities.ParticipationType type, string logicalName)
0xaeb  ldarg.0
0xaec  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0xaf1  ldc.i4.7
0xaf2  ldstr    aOrganizer// "organizer"
0xaf7  callvirt instance void Microsoft.Crm.Entities.PartyMappingCollection::AddMapping(valuetype Microsoft.Crm.Entities.ParticipationType type, string logicalName)
0xafc  ldarg.0
0xafd  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0xb02  ldc.i4.5
0xb03  ldstr    aRequiredattend// "requiredattendees"
0xb08  callvirt instance void Microsoft.Crm.Entities.PartyMappingCollection::AddMapping(valuetype Microsoft.Crm.Entities.ParticipationType type, string logicalName)
0xb0d  ldarg.0
0xb0e  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0xb13  ldc.i4.6
0xb14  ldstr    aOptionalattend// "optionalattendees"
0xb19  callvirt instance void Microsoft.Crm.Entities.PartyMappingCollection::AddMapping(valuetype Microsoft.Crm.Entities.ParticipationType type, string logicalName)
0xb1e  ldarg.0
0xb1f  ldc.i4.s 0xB
0xb21  ldstr    aCustomers// "customers"
0xb26  ldc.i4.1
0xb27  newarr   [mscorlib]System.String
0xb2c  dup
0xb2d  ldc.i4.0
0xb2e  ldstr    aCustomer// "customer"
0xb33  stelem.ref
0xb34  call     instance void Microsoft.Crm.Entities.CommunicationActivity::AddPartyMappingWithAliasedAttributes(valuetype Microsoft.Crm.Entities.ParticipationType participationType, string logicalName, string[] aliasedPartyListAttributeLogicalNames)
0xb39  ldarg.0
0xb3a  ldc.i4.s 0xC
0xb3c  ldstr    aPartners// "partners"
0xb41  ldc.i4.1
0xb42  newarr   [mscorlib]System.String
0xb47  dup
0xb48  ldc.i4.0
0xb49  ldstr    aPartner// "partner"
0xb4e  stelem.ref
0xb4f  call     instance void Microsoft.Crm.Entities.CommunicationActivity::AddPartyMappingWithAliasedAttributes(valuetype Microsoft.Crm.Entities.ParticipationType participationType, string logicalName, string[] aliasedPartyListAttributeLogicalNames)
0xb54  ldarg.0
0xb55  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0xb5a  ldc.i4.s 0xA
0xb5c  ldstr    aResources// "resources"
0xb61  callvirt instance void Microsoft.Crm.Entities.PartyMappingCollection::AddMapping(valuetype Microsoft.Crm.Entities.ParticipationType type, string logicalName)
0xb66  ret
```
