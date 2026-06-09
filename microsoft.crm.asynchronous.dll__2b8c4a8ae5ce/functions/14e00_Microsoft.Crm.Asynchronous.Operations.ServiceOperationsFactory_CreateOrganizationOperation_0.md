# Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::CreateOrganizationOperation_0

- ea: `0x14e00`
- end: `0x14e1a`
- name: `Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::CreateOrganizationOperation_0`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14df0`

## callees

- `0x14ee0`
- `0x14f10`
- `0x152c0`

## pseudocode

```c

```

## disassembly

```asm
0x14e00  ldarg.1
0x14e01  ldarg.2
0x14e02  ldarg.3
0x14e03  ldarg.0
0x14e04  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::get_EventLog()
0x14e09  ldarg.s  4
0x14e0b  newobj   instance void Microsoft.Crm.Asynchronous.Operations.OrganizationOperation::.ctor(string name, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, class Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction eventAction, class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog eventLog, [opt] bool shouldExposeException)
0x14e10  stloc.0
0x14e11  ldarg.0
0x14e12  ldloc.0
0x14e13  call     instance void Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::ApplyBehaviors(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x14e18  ldloc.0
0x14e19  ret
```
