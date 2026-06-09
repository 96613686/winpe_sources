# Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccessFactory::CreateInstance

- ea: `0x7440`
- end: `0x7448`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccessFactory::CreateInstance`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7470`

## pseudocode

```c

```

## disassembly

```asm
0x7440  ldarg.1
0x7441  ldarg.2
0x7442  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager queueManager, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration configuration)
0x7447  ret
```
