# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::CreateActivitiesList

- ea: `0x2f60`
- end: `0x2f7d`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::CreateActivitiesList`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4570`

## callees

- `0x5b10`
- `0x5be0`

## pseudocode

```c

```

## disassembly

```asm
0x2f60  ldarg.0
0x2f61  ldarg.1
0x2f62  ldarg.2
0x2f63  ldarg.3
0x2f64  ldarg.s  4
0x2f66  ldarg.s  5
0x2f68  ldarg.s  6
0x2f6a  ldarg.s  7
0x2f6c  ldarg.s  8
0x2f6e  ldarg.s  9
0x2f70  ldarg.s  0xA
0x2f72  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.CreateActivitiesListCommand::.ctor(valuetype [mscorlib]System.Guid listId, string friendlyName, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity activity, valuetype [mscorlib]System.Guid templateId, bool propagate, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions ownershipOption, valuetype [mscorlib]System.Guid ownerId, int32 ownerType, bool sendEmail, valuetype [mscorlib]System.Guid queueId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2f77  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Application.Platform.ServiceCommands.CreateActivitiesListCommand::Execute()
0x2f7c  ret
```
