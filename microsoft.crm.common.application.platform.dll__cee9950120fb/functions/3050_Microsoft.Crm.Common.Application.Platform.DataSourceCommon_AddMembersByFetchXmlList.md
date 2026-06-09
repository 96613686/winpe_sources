# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddMembersByFetchXmlList

- ea: `0x3050`
- end: `0x305e`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddMembersByFetchXmlList`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4370`

## callees

- `0x5860`
- `0x58b0`

## pseudocode

```c

```

## disassembly

```asm
0x3050  ldarg.0
0x3051  ldarg.1
0x3052  ldarg.2
0x3053  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddMembersByFetchXmlListCommand::.ctor(valuetype [mscorlib]System.Guid listId, string fetchXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3058  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddMembersByFetchXmlListCommand::Execute()
0x305d  ret
```
