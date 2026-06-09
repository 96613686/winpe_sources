# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateOneOperationFromRecurrencePattern

- ea: `0x5060`
- end: `0x5073`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateOneOperationFromRecurrencePattern`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2ee0`

## callees

- `0x2e60`
- `0x7880`

## pseudocode

```c

```

## disassembly

```asm
0x5060  ldarg.0
0x5061  ldarg.1
0x5062  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.AsyncEvent::get_OrganizationConfiguration()
0x5067  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.SynchronousQueueManager`1<class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess>::GetQueueDataAccess(!!T0)
0x506c  ldarg.1
0x506d  callvirt instance void Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess::CreateOneOperationFromRecurrencePattern(class Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0x5072  ret
```
