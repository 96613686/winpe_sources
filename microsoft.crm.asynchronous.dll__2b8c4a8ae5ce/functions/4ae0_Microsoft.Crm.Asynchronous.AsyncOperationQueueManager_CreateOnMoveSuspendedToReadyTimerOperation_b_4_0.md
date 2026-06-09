# Microsoft.Crm.Asynchronous.AsyncOperationQueueManager::<CreateOnMoveSuspendedToReadyTimerOperation>b__4_0

- ea: `0x4ae0`
- end: `0x4b11`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManager::<CreateOnMoveSuspendedToReadyTimerOperation>b__4_0`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x4ae0`
- `0x15810`

## string_xrefs

- `0x4ae1`: `Move to Ready`

## pseudocode

```c

```

## disassembly

```asm
0x4ae0  ldarg.0
0x4ae1  ldstr    aMoveToReady// "Move to Ready"
0x4ae6  ldsfld   class OrganizationQueueDataAccessHandler<class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess> <>c::<>9__4_1
0x4aeb  dup
0x4aec  brtrue.s loc_4B05
0x4aee  pop
0x4aef  ldsfld   class <>c <>c::<>9
0x4af4  ldftn    instance void <>c::<CreateOnMoveSuspendedToReadyTimerOperation>b__4_1(class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess queueDataAccess, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfig)
0x4afa  newobj   instance void class OrganizationQueueDataAccessHandler<class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess>::.ctor(object, native int)
0x4aff  dup
0x4b00  stsfld   class OrganizationQueueDataAccessHandler<class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess> <>c::<>9__4_1
0x4b05  ldc.i4.0
0x4b06  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation class Microsoft.Crm.Asynchronous.SynchronousQueueManager`1<class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess>::CreateQueueManagementOperationForAllOrganization(string, class OrganizationQueueDataAccessHandler<var<u1>>, !!T0)
0x4b0b  callvirt instance void Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x4b10  ret
```
