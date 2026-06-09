# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::ResolveEmailAddress

- ea: `0x3160`
- end: `0x316e`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::ResolveEmailAddress`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6330`
- `0x6360`

## pseudocode

```c

```

## disassembly

```asm
0x3160  ldarg.0
0x3161  ldarg.1
0x3162  ldarg.2
0x3163  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.ResolveEmailAddressCommand::.ctor(string emailAddresses, int32[] objectTypeCodes, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3168  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Common.Application.Platform.ServiceCommands.ResolveEmailAddressCommand::Execute()
0x316d  ret
```
