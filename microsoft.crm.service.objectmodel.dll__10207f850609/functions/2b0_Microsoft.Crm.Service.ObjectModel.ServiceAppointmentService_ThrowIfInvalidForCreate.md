# Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::ThrowIfInvalidForCreate

- ea: `0x2b0`
- end: `0x2e9`
- name: `Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::ThrowIfInvalidForCreate`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2b0`

## string_xrefs

- `0x2b1`: `scheduledstart`
- `0x2be`: `scheduledstart`
- `0x2c9`: `scheduledend`
- `0x2d6`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x2b0  ldarg.1
0x2b1  ldstr    aScheduledstart// "scheduledstart"
0x2b6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x2bb  brfalse.s loc_2C8
0x2bd  ldnull
0x2be  ldstr    aScheduledstart// "scheduledstart"
0x2c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2c8  ldarg.1
0x2c9  ldstr    aScheduledend// "scheduledend"
0x2ce  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x2d3  brfalse.s loc_2E0
0x2d5  ldnull
0x2d6  ldstr    aScheduledend// "scheduledend"
0x2db  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e0  ldarg.0
0x2e1  ldarg.1
0x2e2  ldarg.2
0x2e3  call     instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.GenericActivityServiceBase::ThrowIfInvalidForCreate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2e8  ret
```
