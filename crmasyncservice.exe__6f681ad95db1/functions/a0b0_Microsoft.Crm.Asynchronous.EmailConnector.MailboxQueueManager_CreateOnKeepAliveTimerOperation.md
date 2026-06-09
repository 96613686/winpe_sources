# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::CreateOnKeepAliveTimerOperation

- ea: `0xa0b0`
- end: `0xa0f8`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::CreateOnKeepAliveTimerOperation`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9f40`

## callees

- `0xba70`

## pseudocode

```c

```

## disassembly

```asm
0xa0b0  newobj   instance void <>c__DisplayClass16_0::.ctor()
0xa0b5  stloc.0
0xa0b6  ldloc.0
0xa0b7  ldarg.0
0xa0b8  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager <>c__DisplayClass16_0::<>4__this
0xa0bd  ldloc.0
0xa0be  ldarg.0
0xa0bf  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0xa0c4  ldstr    aKeepalive// "_KeepAlive"
0xa0c9  call     string [mscorlib]System.String::Concat(string, string)
0xa0ce  stfld    string <>c__DisplayClass16_0::operationName
0xa0d3  ldarg.0
0xa0d4  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0xa0d9  ldarg.0
0xa0da  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0xa0df  ldloc.0
0xa0e0  ldfld    string <>c__DisplayClass16_0::operationName
0xa0e5  ldloc.0
0xa0e6  ldftn    instance void <>c__DisplayClass16_0::<CreateOnKeepAliveTimerOperation>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0xa0ec  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0xa0f1  ldnull
0xa0f2  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string, string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0xa0f7  ret
```
