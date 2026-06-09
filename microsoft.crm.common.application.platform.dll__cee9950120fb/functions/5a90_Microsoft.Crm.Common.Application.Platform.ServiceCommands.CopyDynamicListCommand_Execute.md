# Microsoft.Crm.Common.Application.Platform.ServiceCommands.CopyDynamicListCommand::Execute

- ea: `0x5a90`
- end: `0x5aa1`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.CopyDynamicListCommand::Execute`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2fa0`

## pseudocode

```c

```

## disassembly

```asm
0x5a90  ldarg.0
0x5a91  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x5a96  isinst   [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CopyDynamicListToStaticResponse
0x5a9b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CopyDynamicListToStaticResponse::get_StaticListId()
0x5aa0  ret
```
