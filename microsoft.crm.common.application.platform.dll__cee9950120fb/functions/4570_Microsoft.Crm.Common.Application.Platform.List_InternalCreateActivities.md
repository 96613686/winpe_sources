# Microsoft.Crm.Common.Application.Platform.List::InternalCreateActivities

- ea: `0x4570`
- end: `0x45c1`
- name: `Microsoft.Crm.Common.Application.Platform.List::InternalCreateActivities`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4530`
- `0x4550`

## callees

- `0x2f60`

## pseudocode

```c

```

## disassembly

```asm
0x4570  ldarg.s  4
0x4572  ldarg.0
0x4573  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x4578  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x457d  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4582  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x4587  ldarg.0
0x4588  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x458d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x4592  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4597  stloc.0
0x4598  ldloc.0
0x4599  ldarg.3
0x459a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0x459f  ldarg.1
0x45a0  ldarg.2
0x45a1  ldloc.0
0x45a2  ldarg.s  5
0x45a4  ldarg.s  6
0x45a6  ldarg.s  7
0x45a8  ldarg.s  8
0x45aa  ldarg.s  9
0x45ac  ldarg.s  0xA
0x45ae  ldarg.s  0xB
0x45b0  ldarg.0
0x45b1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x45b6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x45bb  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Application.Platform.DataSourceCommon::CreateActivitiesList(valuetype [mscorlib]System.Guid listId, string friendlyName, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity activity, valuetype [mscorlib]System.Guid templateId, bool propagate, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions ownershipOption, valuetype [mscorlib]System.Guid ownerId, int32 ownerType, bool sendEmail, valuetype [mscorlib]System.Guid queueId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x45c0  ret
```
