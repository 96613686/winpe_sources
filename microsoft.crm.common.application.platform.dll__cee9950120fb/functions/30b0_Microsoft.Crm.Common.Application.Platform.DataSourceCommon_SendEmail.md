# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendEmail

- ea: `0x30b0`
- end: `0x30be`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::SendEmail`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3e30`

## callees

- `0x63a0`
- `0x63e0`

## pseudocode

```c

```

## disassembly

```asm
0x30b0  ldarg.0
0x30b1  ldarg.1
0x30b2  ldarg.2
0x30b3  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendEmailCommand::.ctor(valuetype [mscorlib]System.Guid emailId, string trackingToken, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30b8  call     instance string Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendEmailCommand::Execute()
0x30bd  ret
```
