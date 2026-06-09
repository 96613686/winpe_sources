# Microsoft.Crm.Entities.ServiceAppointment::get_BlockingParties

- ea: `0xee0`
- end: `0xf00`
- name: `Microsoft.Crm.Entities.ServiceAppointment::get_BlockingParties`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xea0`
- `0xee0`

## pseudocode

```c

```

## disassembly

```asm
0xee0  ldarg.0
0xee1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.ServiceAppointment::get_Resources()
0xee6  brfalse.s loc_EEF
0xee8  ldarg.0
0xee9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.ServiceAppointment::get_Resources()
0xeee  ret
0xeef  ldstr    aActivityparty// "ActivityParty"
0xef4  ldarg.0
0xef5  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_OrganizationId()
0xefa  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0xeff  ret
```
