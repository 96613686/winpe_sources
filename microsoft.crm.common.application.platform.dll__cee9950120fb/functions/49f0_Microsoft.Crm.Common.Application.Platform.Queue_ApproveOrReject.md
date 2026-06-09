# Microsoft.Crm.Common.Application.Platform.Queue::ApproveOrReject

- ea: `0x49f0`
- end: `0x4a4d`
- name: `Microsoft.Crm.Common.Application.Platform.Queue::ApproveOrReject`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x49f0`

## string_xrefs

- `0x4a21`: `emailrouteraccessapproval`

## pseudocode

```c

```

## disassembly

```asm
0x49f0  ldstr    aQueue// "queue"
0x49f5  ldarg.0
0x49f6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x49fb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x4a00  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4a05  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x4a0a  dup
0x4a0b  ldstr    aQueueid// "queueid"
0x4a10  ldarg.1
0x4a11  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4a16  box      [mscorlib]System.Guid
0x4a1b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4a20  dup
0x4a21  ldstr    aEmailrouteracc// "emailrouteraccessapproval"
0x4a26  ldarg.2
0x4a27  brtrue.s loc_4A2C
0x4a29  ldc.i4.3
0x4a2a  br.s     loc_4A2D
0x4a2c  ldc.i4.1
0x4a2d  box      [mscorlib]System.Int32
0x4a32  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4a37  ldarg.0
0x4a38  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x4a3d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x4a42  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.UpdateCommand::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4a47  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.UpdateCommand::Execute()
0x4a4c  ret
```
