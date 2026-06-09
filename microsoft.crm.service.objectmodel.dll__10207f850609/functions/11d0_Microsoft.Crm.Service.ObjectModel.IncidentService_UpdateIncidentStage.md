# Microsoft.Crm.Service.ObjectModel.IncidentService::UpdateIncidentStage

- ea: `0x11d0`
- end: `0x1210`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::UpdateIncidentStage`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2200`

## callees

- `0x11d0`
- `0x18b0`

## string_xrefs

- `0x11f7`: `servicestage`

## pseudocode

```c

```

## disassembly

```asm
0x11d0  ldarg.0
0x11d1  ldarg.3
0x11d2  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::HasServiceStage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x11d7  brfalse.s loc_120F
0x11d9  ldarg.3
0x11da  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11df  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident::.ctor(valuetype [mscorlib]System.Guid)
0x11e4  stloc.0
0x11e5  ldloc.0
0x11e6  ldstr    aIncidentid// "incidentid"
0x11eb  ldarg.1
0x11ec  box      [mscorlib]System.Guid
0x11f1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x11f6  ldloc.0
0x11f7  ldstr    aServicestage// "servicestage"
0x11fc  ldarg.2
0x11fd  box      [mscorlib]System.Int32
0x1202  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1207  ldarg.0
0x1208  ldloc.0
0x1209  ldarg.3
0x120a  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x120f  ret
```
