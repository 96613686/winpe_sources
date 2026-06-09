# Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::Validate

- ea: `0x4f0`
- end: `0x539`
- name: `Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::Validate`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4f0`

## string_xrefs

- `0x4f6`: `ServiceAppointment`
- `0x507`: `Expected collection of serviceappointments, received collection of {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x4f0  ldarg.1
0x4f1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_EntityName()
0x4f6  ldstr    aServiceappoint// "ServiceAppointment"
0x4fb  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x500  brfalse.s loc_52B
0x502  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x507  ldstr    aExpectedCollec// "Expected collection of serviceappointme"...
0x50c  ldc.i4.1
0x50d  newarr   [mscorlib]System.Object
0x512  dup
0x513  ldc.i4.0
0x514  ldarg.1
0x515  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_EntityName()
0x51a  stelem.ref
0x51b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x520  ldstr    aAppointment// "appointment"
0x525  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x52a  throw
0x52b  ldarg.0
0x52c  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ScheduleService Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::_scheduleService
0x531  ldarg.1
0x532  ldarg.2
0x533  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ValidationResult[] [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ScheduleService::Validate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x538  ret
```
