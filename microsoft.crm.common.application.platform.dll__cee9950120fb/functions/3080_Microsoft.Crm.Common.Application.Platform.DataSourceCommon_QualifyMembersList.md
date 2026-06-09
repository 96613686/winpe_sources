# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QualifyMembersList

- ea: `0x3080`
- end: `0x308f`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QualifyMembersList`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6110`
- `0x6150`

## pseudocode

```c

```

## disassembly

```asm
0x3080  ldarg.0
0x3081  ldarg.1
0x3082  ldarg.2
0x3083  ldarg.3
0x3084  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyMembersListCommand::.ctor(valuetype [mscorlib]System.Guid listId, valuetype [mscorlib]System.Guid[] memberIds, bool overrideOrRemove, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3089  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.QualifyMembersListCommand::Execute()
0x308e  ret
```
