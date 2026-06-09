# Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendEmailCommand::Execute

- ea: `0x63e0`
- end: `0x63f1`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.SendEmailCommand::Execute`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x30b0`

## pseudocode

```c

```

## disassembly

```asm
0x63e0  ldarg.0
0x63e1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x63e6  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailResponse
0x63eb  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.SendEmailResponse::get_Subject()
0x63f0  ret
```
