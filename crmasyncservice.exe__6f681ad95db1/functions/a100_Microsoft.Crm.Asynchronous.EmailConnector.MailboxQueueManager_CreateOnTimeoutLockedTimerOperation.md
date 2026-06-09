# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::CreateOnTimeoutLockedTimerOperation

- ea: `0xa100`
- end: `0xa148`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::CreateOnTimeoutLockedTimerOperation`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9f40`

## callees

- `0xbb50`

## pseudocode

```c

```

## disassembly

```asm
0xa100  newobj   instance void <>c__DisplayClass17_0::.ctor()
0xa105  stloc.0
0xa106  ldloc.0
0xa107  ldarg.0
0xa108  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager <>c__DisplayClass17_0::<>4__this
0xa10d  ldloc.0
0xa10e  ldarg.0
0xa10f  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0xa114  ldstr    aTimeoutlocked// "_TimeoutLocked"
0xa119  call     string [mscorlib]System.String::Concat(string, string)
0xa11e  stfld    string <>c__DisplayClass17_0::operationName
0xa123  ldarg.0
0xa124  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_OperationsFactory()
0xa129  ldarg.0
0xa12a  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0xa12f  ldloc.0
0xa130  ldfld    string <>c__DisplayClass17_0::operationName
0xa135  ldloc.0
0xa136  ldftn    instance void <>c__DisplayClass17_0::<CreateOnTimeoutLockedTimerOperation>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0xa13c  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0xa141  ldnull
0xa142  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateQueueManagementOperation(string, string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0xa147  ret
```
