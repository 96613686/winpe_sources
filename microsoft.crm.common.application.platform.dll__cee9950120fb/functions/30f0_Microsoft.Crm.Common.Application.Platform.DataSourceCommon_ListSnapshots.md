# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::ListSnapshots

- ea: `0x30f0`
- end: `0x30ff`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::ListSnapshots`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5c80`
- `0x5cb0`

## pseudocode

```c

```

## disassembly

```asm
0x30f0  ldarg.0
0x30f1  ldarg.3
0x30f2  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.ListSnapshotsCommand::.ctor(valuetype [mscorlib]System.Guid reportId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30f7  ldarg.1
0x30f8  ldarg.2
0x30f9  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.ListSnapshotsCommand::Execute([out] string[]& historyIds, [out] valuetype [mscorlib]System.DateTime[]& createdDates)
0x30fe  ret
```
