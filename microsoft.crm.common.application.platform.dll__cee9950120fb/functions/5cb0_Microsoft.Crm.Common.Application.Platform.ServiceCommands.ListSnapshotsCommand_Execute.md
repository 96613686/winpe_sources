# Microsoft.Crm.Common.Application.Platform.ServiceCommands.ListSnapshotsCommand::Execute

- ea: `0x5cb0`
- end: `0x5ccd`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.ListSnapshotsCommand::Execute`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x30f0`

## pseudocode

```c

```

## disassembly

```asm
0x5cb0  ldarg.0
0x5cb1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::XrmExecuteInternal()
0x5cb6  isinst   [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ListSnapshotsResponse
0x5cbb  stloc.0
0x5cbc  ldarg.1
0x5cbd  ldloc.0
0x5cbe  callvirt instance string[] [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ListSnapshotsResponse::get_HistoryIds()
0x5cc3  stind.ref
0x5cc4  ldarg.2
0x5cc5  ldloc.0
0x5cc6  callvirt instance valuetype [mscorlib]System.DateTime[] [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.Internal.ListSnapshotsResponse::get_CreatedDates()
0x5ccb  stind.ref
0x5ccc  ret
```
