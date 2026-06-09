# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RemoveMembersByFetchXmlList

- ea: `0x2fc0`
- end: `0x2fcf`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RemoveMembersByFetchXmlList`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4350`

## callees

- `0x62b0`
- `0x6310`

## pseudocode

```c

```

## disassembly

```asm
0x2fc0  ldarg.0
0x2fc1  ldarg.1
0x2fc2  ldarg.2
0x2fc3  ldarg.3
0x2fc4  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.RemoveMembersByFetchXmlListCommand::.ctor(valuetype [mscorlib]System.Guid listId, string fetchXml, bool keepReturned, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2fc9  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.RemoveMembersByFetchXmlListCommand::Execute()
0x2fce  ret
```
