# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendFax

- ea: `0x30c0`
- end: `0x30cd`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendFax`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x40d0`

## callees

- `0x6410`
- `0x6440`

## pseudocode

```c

```

## disassembly

```asm
0x30c0  ldarg.0
0x30c1  ldarg.1
0x30c2  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendFaxCommand::.ctor(valuetype [mscorlib]System.Guid faxId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30c7  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendFaxCommand::Execute()
0x30cc  ret
```
