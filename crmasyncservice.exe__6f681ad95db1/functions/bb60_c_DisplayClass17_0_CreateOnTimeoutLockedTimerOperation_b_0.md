# <>c__DisplayClass17_0::<CreateOnTimeoutLockedTimerOperation>b__0

- ea: `0xbb60`
- end: `0xbb97`
- name: `<>c__DisplayClass17_0::<CreateOnTimeoutLockedTimerOperation>b__0`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xbb60`

## pseudocode

```c

```

## disassembly

```asm
0xbb60  ldarg.0
0xbb61  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager <>c__DisplayClass17_0::<>4__this
0xbb66  ldarg.0
0xbb67  ldfld    string <>c__DisplayClass17_0::operationName
0xbb6c  ldsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1/OrganizationQueueDataAccessHandler<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess> <>c::<>9__17_1
0xbb71  dup
0xbb72  brtrue.s loc_BB8B
0xbb74  pop
0xbb75  ldsfld   class <>c <>c::<>9
0xbb7a  ldftn    instance void <>c::<CreateOnTimeoutLockedTimerOperation>b__17_1(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess queueDataAccess, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfig)
0xbb80  newobj   instance void class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1/OrganizationQueueDataAccessHandler<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess>::.ctor(object, native int)
0xbb85  dup
0xbb86  stsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1/OrganizationQueueDataAccessHandler<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess> <>c::<>9__17_1
0xbb8b  ldc.i4.0
0xbb8c  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueDataAccess>::CreateQueueManagementOperationForAllOrganization(string, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SynchronousQueueManager`1/OrganizationQueueDataAccessHandler<var<u1>>, !!T0)
0xbb91  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0xbb96  ret
```
