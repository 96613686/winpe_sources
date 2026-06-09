# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendTemplate

- ea: `0x30d0`
- end: `0x30e7`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendTemplate`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5070`
- `0x5110`

## callees

- `0x6460`
- `0x64d0`

## pseudocode

```c

```

## disassembly

```asm
0x30d0  ldarg.0
0x30d1  ldarg.1
0x30d2  ldarg.2
0x30d3  ldarg.3
0x30d4  ldarg.s  4
0x30d6  ldarg.s  5
0x30d8  ldarg.s  6
0x30da  ldarg.s  7
0x30dc  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendTemplateCommand::.ctor(valuetype [mscorlib]System.Guid templateId, valuetype [mscorlib]System.Guid[] recipients, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType recipientType, valuetype [mscorlib]System.Guid regardingId, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType regardingType, valuetype [mscorlib]System.Guid senderId, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType senderType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30e1  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendTemplateCommand::Execute()
0x30e6  ret
```
