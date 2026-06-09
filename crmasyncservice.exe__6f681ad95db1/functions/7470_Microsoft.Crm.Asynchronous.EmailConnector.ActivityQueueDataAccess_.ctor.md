# Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::.ctor

- ea: `0x7470`
- end: `0x7490`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::.ctor`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x7440`

## pseudocode

```c

```

## disassembly

```asm
0x7470  ldarg.0
0x7471  ldarg.2
0x7472  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0x7477  ldarg.0
0x7478  ldarg.1
0x7479  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x747e  ldarg.0
0x747f  ldarg.0
0x7480  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x7485  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x748a  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_operationsFactory
0x748f  ret
```
