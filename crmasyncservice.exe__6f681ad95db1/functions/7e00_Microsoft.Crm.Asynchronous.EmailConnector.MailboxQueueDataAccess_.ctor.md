# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::.ctor

- ea: `0x7e00`
- end: `0x7e3b`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::.ctor`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x96c0`
- `0xa1a0`

## pseudocode

```c

```

## disassembly

```asm
0x7e00  ldarg.0
0x7e01  ldarg.2
0x7e02  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0x7e07  ldarg.0
0x7e08  ldarg.1
0x7e09  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x7e0e  ldarg.0
0x7e0f  ldarg.0
0x7e10  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x7e15  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0x7e1a  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_operationsFactory
0x7e1f  ldarg.0
0x7e20  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.VersionService::.ctor()
0x7e25  ldarg.2
0x7e26  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x7e2b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x7e30  call     instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.VersionService::RetrieveVersion(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7e35  stfld    string Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::versionNumber
0x7e3a  ret
```
