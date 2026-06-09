# Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::ResolveUnresolvedParties

- ea: `0x570`
- end: `0x5de`
- name: `Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::ResolveUnresolvedParties`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x570`

## string_xrefs

- `0x57f`: `Reschedule expected serviceappointment entity, received {0}`

## pseudocode

```c

```

## disassembly

```asm
0x570  ldarg.1
0x571  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment
0x576  stloc.0
0x577  ldloc.0
0x578  brtrue.s loc_5A3
0x57a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x57f  ldstr    aRescheduleExpe// "Reschedule expected serviceappointment "...
0x584  ldc.i4.1
0x585  newarr   [mscorlib]System.Object
0x58a  dup
0x58b  ldc.i4.0
0x58c  ldarg.1
0x58d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x592  stelem.ref
0x593  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x598  ldstr    aAppointment// "appointment"
0x59d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x5a2  throw
0x5a3  ldarg.0
0x5a4  ldloc.0
0x5a5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment::get_Resources()
0x5aa  ldc.i4.2
0x5ab  newarr   [mscorlib]System.Int32
0x5b0  dup
0x5b1  ldc.i4.0
0x5b2  ldc.i4.8
0x5b3  stelem.i4
0x5b4  dup
0x5b5  ldc.i4.1
0x5b6  ldc.i4   0xFA0
0x5bb  stelem.i4
0x5bc  ldarg.2
0x5bd  call     instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::ResolveUnresolvedParties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection, int32[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5c2  ldarg.0
0x5c3  ldloc.0
0x5c4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment::get_Customers()
0x5c9  ldc.i4.2
0x5ca  newarr   [mscorlib]System.Int32
0x5cf  dup
0x5d0  ldc.i4.0
0x5d1  ldc.i4.2
0x5d2  stelem.i4
0x5d3  dup
0x5d4  ldc.i4.1
0x5d5  ldc.i4.1
0x5d6  stelem.i4
0x5d7  ldarg.2
0x5d8  call     instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::ResolveUnresolvedParties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection, int32[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5dd  ret
```
