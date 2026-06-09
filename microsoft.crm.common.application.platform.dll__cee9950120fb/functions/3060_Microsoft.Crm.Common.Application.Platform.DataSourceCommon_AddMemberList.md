# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddMemberList

- ea: `0x3060`
- end: `0x306f`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddMemberList`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5800`
- `0x5830`

## pseudocode

```c

```

## disassembly

```asm
0x3060  ldarg.0
0x3061  ldarg.1
0x3062  ldarg.2
0x3063  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddMemberListCommand::.ctor(valuetype [mscorlib]System.Guid listId, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3068  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddMemberListCommand::Execute()
0x306d  pop
0x306e  ret
```
