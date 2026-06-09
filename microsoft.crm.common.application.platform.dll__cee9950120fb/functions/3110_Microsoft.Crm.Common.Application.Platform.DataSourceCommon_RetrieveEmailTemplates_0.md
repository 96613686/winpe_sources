# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RetrieveEmailTemplates_0

- ea: `0x3110`
- end: `0x311e`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RetrieveEmailTemplates_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x66e0`

## pseudocode

```c

```

## disassembly

```asm
0x3110  ldarg.0
0x3111  ldarg.1
0x3112  ldarg.2
0x3113  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveEmailTemplatesCommand::.ctor(int32 languageCode, int32 templateTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3118  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ExecuteFetchCommand::Execute()
0x311d  ret
```
