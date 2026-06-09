# Microsoft.Crm.Workflow.Services.ActivityServiceBase::RetrieveEntityInternal

- ea: `0x14e90`
- end: `0x14e9f`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::RetrieveEntityInternal`
- size: `15`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e7c0`
- `0x2ea90`
- `0x2ed90`
- `0x2ee70`
- `0x2f0e0`
- `0x2f190`

## pseudocode

```c

```

## disassembly

```asm
0x14e90  ldarg.3
0x14e91  ldarg.1
0x14e92  ldarg.2
0x14e93  ldc.i4.1
0x14e94  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool)
0x14e99  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x14e9e  ret
```
