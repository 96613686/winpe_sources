# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::CopyMembersList

- ea: `0x2fb0`
- end: `0x2fbe`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::CopyMembersList`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4330`

## callees

- `0x5ac0`
- `0x5af0`

## pseudocode

```c

```

## disassembly

```asm
0x2fb0  ldarg.0
0x2fb1  ldarg.1
0x2fb2  ldarg.2
0x2fb3  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.CopyMembersListCommand::.ctor(valuetype [mscorlib]System.Guid sourceListId, valuetype [mscorlib]System.Guid destinationListId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2fb8  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.CopyMembersListCommand::Execute()
0x2fbd  ret
```
