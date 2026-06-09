# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddMembersList

- ea: `0x3070`
- end: `0x307e`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddMembersList`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x58d0`
- `0x5900`

## pseudocode

```c

```

## disassembly

```asm
0x3070  ldarg.0
0x3071  ldarg.1
0x3072  ldarg.2
0x3073  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddMembersListCommand::.ctor(valuetype [mscorlib]System.Guid listId, valuetype [mscorlib]System.Guid[] memberIds, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3078  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddMembersListCommand::Execute()
0x307d  ret
```
