# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::CreateReportEventsOperation

- ea: `0xa150`
- end: `0xa198`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::CreateReportEventsOperation`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9f40`

## callees

- `0xbbb0`

## pseudocode

```c

```

## disassembly

```asm
0xa150  newobj   instance void <>c__DisplayClass18_0::.ctor()
0xa155  stloc.0
0xa156  ldloc.0
0xa157  ldarg.0
0xa158  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager <>c__DisplayClass18_0::<>4__this
0xa15d  ldloc.0
0xa15e  ldarg.0
0xa15f  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0xa164  ldstr    aReportevents_0// "_ReportEvents"
0xa169  call     string [mscorlib]System.String::Concat(string, string)
0xa16e  stfld    string <>c__DisplayClass18_0::operationName
0xa173  ldarg.0
0xa174  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0xa179  ldarg.0
0xa17a  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0xa17f  ldloc.0
0xa180  ldfld    string <>c__DisplayClass18_0::operationName
0xa185  ldloc.0
0xa186  ldftn    instance void <>c__DisplayClass18_0::<CreateReportEventsOperation>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0xa18c  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0xa191  ldnull
0xa192  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string, string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0xa197  ret
```
