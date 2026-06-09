# <>c__DisplayClass16_0::<CreateOnKeepAliveTimerOperation>b__0

- ea: `0xba80`
- end: `0xbab7`
- name: `<>c__DisplayClass16_0::<CreateOnKeepAliveTimerOperation>b__0`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xba80`

## pseudocode

```c

```

## disassembly

```asm
0xba80  ldarg.0
0xba81  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager <>c__DisplayClass16_0::<>4__this
0xba86  ldarg.0
0xba87  ldfld    string <>c__DisplayClass16_0::operationName
0xba8c  ldsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1/OrganizationQueueDataAccessHandler<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess> <>c::<>9__16_1
0xba91  dup
0xba92  brtrue.s loc_BAAB
0xba94  pop
0xba95  ldsfld   class <>c <>c::<>9
0xba9a  ldftn    instance void <>c::<CreateOnKeepAliveTimerOperation>b__16_1(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess queueDataAccess, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfig)
0xbaa0  newobj   instance void class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1/OrganizationQueueDataAccessHandler<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess>::.ctor(object, native int)
0xbaa5  dup
0xbaa6  stsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1/OrganizationQueueDataAccessHandler<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess> <>c::<>9__16_1
0xbaab  ldc.i4.0
0xbaac  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess>::CreateQueueManagementOperationForAllOrganization(string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1/OrganizationQueueDataAccessHandler<var<u1>>, !!T0)
0xbab1  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0xbab6  ret
```
