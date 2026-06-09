# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RetrieveEmailTemplates

- ea: `0x3100`
- end: `0x310d`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RetrieveEmailTemplates`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x66d0`

## pseudocode

```c

```

## disassembly

```asm
0x3100  ldarg.0
0x3101  ldarg.1
0x3102  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveEmailTemplatesCommand::.ctor(int32 templateTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3107  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ExecuteFetchCommand::Execute()
0x310c  ret
```
