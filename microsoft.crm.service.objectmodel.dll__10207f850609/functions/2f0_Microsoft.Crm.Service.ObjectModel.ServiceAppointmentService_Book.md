# Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::Book

- ea: `0x2f0`
- end: `0x339`
- name: `Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::Book`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2f0`

## string_xrefs

- `0x2ff`: `Book expected serviceappointment entity, received {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2f0  ldarg.1
0x2f1  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment
0x2f6  stloc.0
0x2f7  ldloc.0
0x2f8  brtrue.s loc_323
0x2fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ff  ldstr    aBookExpectedSe// "Book expected serviceappointment entity"...
0x304  ldc.i4.1
0x305  newarr   [mscorlib]System.Object
0x30a  dup
0x30b  ldc.i4.0
0x30c  ldarg.1
0x30d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x312  stelem.ref
0x313  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x318  ldstr    aAppointment// "appointment"
0x31d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x322  throw
0x323  ldarg.0
0x324  ldloc.0
0x325  ldarg.2
0x326  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::ResolveUnresolvedParties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x32b  ldarg.0
0x32c  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ScheduleService Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::_scheduleService
0x331  ldloc.0
0x332  ldarg.2
0x333  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ValidationResult [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ScheduleService::Book(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CommunicationActivity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x338  ret
```
