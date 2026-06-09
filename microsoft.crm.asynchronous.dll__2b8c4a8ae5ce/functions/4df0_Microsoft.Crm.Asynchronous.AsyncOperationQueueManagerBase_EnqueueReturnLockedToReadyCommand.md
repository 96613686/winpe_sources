# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::EnqueueReturnLockedToReadyCommand

- ea: `0x4df0`
- end: `0x4e54`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::EnqueueReturnLockedToReadyCommand`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x4a70`

## callees

- `0x4bd0`
- `0x4df0`
- `0x4e60`
- `0x168c0`

## pseudocode

```c

```

## disassembly

```asm
0x4df0  newobj   instance void class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand>::.ctor()
0x4df5  stloc.0
0x4df6  ldarg.0
0x4df7  call     instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x4dfc  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::get_Organizations()
0x4e01  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>>::GetEnumerator()
0x4e06  stloc.1
0x4e07  br.s     loc_4E38
0x4e09  ldloc.1
0x4e0a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>>::get_Current()
0x4e0f  stloc.2
0x4e10  ldloca.s 2
0x4e12  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Value()
0x4e17  stloc.3
0x4e18  ldloc.3
0x4e19  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationState()
0x4e1e  ldc.i4.1
0x4e1f  bne.un.s loc_4E38
0x4e21  ldarg.0
0x4e22  ldloc.3
0x4e23  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.SynchronousQueueManager`1<class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess>::GetQueueDataAccess(!!T0)
0x4e28  ldloc.3
0x4e29  newobj   instance void ReturnLockedToReadyOnStartUpCommand::.ctor(class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess queueDataAccess, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfig)
0x4e2e  stloc.s  4
0x4e30  ldloc.0
0x4e31  ldloc.s  4
0x4e33  callvirt instance void class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand>::Enqueue(var<u1>)
0x4e38  ldloc.1
0x4e39  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4e3e  brtrue.s loc_4E09
0x4e40  leave.s  loc_4E4C
0x4e42  ldloc.1
0x4e43  brfalse.s loc_4E4B
0x4e45  ldloc.1
0x4e46  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e4b  endfinally
0x4e4c  ldarg.0
0x4e4d  ldloc.0
0x4e4e  call     instance void Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::EnqueueDatabaseCommandsFromQueue(class [System]System.Collections.Generic.Queue`1<class Microsoft.Crm.Asynchronous.QueuedDatabaseCommand> queue)
0x4e53  ret
```
