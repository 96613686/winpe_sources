# Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemPickCommand::Execute

- ea: `0xf0`
- end: `0xf8`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemPickCommand::Execute`
- size: `8`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3010`

## pseudocode

```c

```

## disassembly

```asm
0xf0  ldarg.0
0xf1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0xf6  pop
0xf7  ret
```
