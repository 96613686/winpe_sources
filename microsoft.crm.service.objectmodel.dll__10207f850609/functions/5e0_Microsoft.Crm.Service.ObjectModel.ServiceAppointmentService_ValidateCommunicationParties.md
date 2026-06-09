# Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::ValidateCommunicationParties

- ea: `0x5e0`
- end: `0x637`
- name: `Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::ValidateCommunicationParties`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x5e0`

## string_xrefs

- `0x5f2`: `Invalid Activity object supplied for validation of Communication Parties`

## pseudocode

```c

```

## disassembly

```asm
0x5e0  ldarg.0
0x5e1  ldarg.1
0x5e2  ldarg.2
0x5e3  call     instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::ValidateCommunicationParties(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CommunicationActivity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5e8  ldarg.1
0x5e9  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment
0x5ee  stloc.0
0x5ef  ldloc.0
0x5f0  brtrue.s loc_5FD
0x5f2  ldstr    aInvalidActivit// "Invalid Activity object supplied for va"...
0x5f7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x5fc  throw
0x5fd  ldarg.0
0x5fe  ldloc.0
0x5ff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment::get_Customers()
0x604  ldloc.0
0x605  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::ValidatePartyNotQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CommunicationActivity)
0x60a  ldarg.0
0x60b  ldloc.0
0x60c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment::get_Resources()
0x611  ldloc.0
0x612  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::ValidatePartyNotQueue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CommunicationActivity)
0x617  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ParticipationType>::.ctor()
0x61c  stloc.1
0x61d  ldloc.1
0x61e  ldc.i4.s 0xB
0x620  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ParticipationType>::Add(var<u1>)
0x625  ldloc.1
0x626  ldc.i4.s 0xA
0x628  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ParticipationType>::Add(var<u1>)
0x62d  ldarg.0
0x62e  ldloc.0
0x62f  ldloc.1
0x630  ldarg.2
0x631  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::SetEmailAddressForParties(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CommunicationActivity, class [mscorlib]System.Collections.Generic.IList`1<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ParticipationType>, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x636  ret
```
