# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::GetEvents

- ea: `0x7ec0`
- end: `0x7f05`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::GetEvents`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x7e40`

## callees

- `0x7ca0`
- `0x7ec0`

## pseudocode

```c

```

## disassembly

```asm
0x7ec0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::.ctor()
0x7ec5  stloc.0
0x7ec6  ldc.i4.0
0x7ec7  stloc.1
0x7ec8  br.s     loc_7EFA
0x7eca  ldarg.1
0x7ecb  ldloc.1
0x7ecc  call     T0x2B00001A
0x7ed1  ldarg.0
0x7ed2  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x7ed7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x7edc  ldc.i4.s 0x33
0x7ede  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailboxAsyncEvent::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailBoxEntityWrapper, valuetype [mscorlib]System.Guid, int32)
0x7ee3  stloc.2
0x7ee4  ldloc.0
0x7ee5  ldarg.0
0x7ee6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x7eeb  ldloc.2
0x7eec  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxExecutionManager::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager queueManager, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailboxAsyncEvent asyncEvent)
0x7ef1  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::Add(var<u1>)
0x7ef6  ldloc.1
0x7ef7  ldc.i4.1
0x7ef8  add
0x7ef9  stloc.1
0x7efa  ldloc.1
0x7efb  ldarg.1
0x7efc  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailBoxEntityWrapper>::get_Count()
0x7f01  blt.s    loc_7ECA
0x7f03  ldloc.0
0x7f04  ret
```
