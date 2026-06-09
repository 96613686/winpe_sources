# <>c__DisplayClass18_0::<CreateReportEventsOperation>b__0

- ea: `0xbbc0`
- end: `0xbbf7`
- name: `<>c__DisplayClass18_0::<CreateReportEventsOperation>b__0`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xbbc0`

## pseudocode

```c

```

## disassembly

```asm
0xbbc0  ldarg.0
0xbbc1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager <>c__DisplayClass18_0::<>4__this
0xbbc6  ldarg.0
0xbbc7  ldfld    string <>c__DisplayClass18_0::operationName
0xbbcc  ldsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1/OrganizationQueueDataAccessHandler<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess> <>c::<>9__18_1
0xbbd1  dup
0xbbd2  brtrue.s loc_BBEB
0xbbd4  pop
0xbbd5  ldsfld   class <>c <>c::<>9
0xbbda  ldftn    instance void <>c::<CreateReportEventsOperation>b__18_1(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess queueDataAccess, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfig)
0xbbe0  newobj   instance void class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1/OrganizationQueueDataAccessHandler<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess>::.ctor(object, native int)
0xbbe5  dup
0xbbe6  stsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1/OrganizationQueueDataAccessHandler<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess> <>c::<>9__18_1
0xbbeb  ldc.i4.0
0xbbec  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess>::CreateQueueManagementOperationForAllOrganization(string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1/OrganizationQueueDataAccessHandler<var<u1>>, !!T0)
0xbbf1  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0xbbf6  ret
```
