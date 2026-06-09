# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::GetAsyncEventIdOfLongProcessingMailbox

- ea: `0x8410`
- end: `0x8486`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::GetAsyncEventIdOfLongProcessingMailbox`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xb1c0`

## callees

- `0x8410`
- `0x9f10`
- `0x9f20`
- `0x9f30`

## pseudocode

```c

```

## disassembly

```asm
0x8410  ldarg.0
0x8411  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x8416  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::GetExecutingOperationsMapping()
0x841b  stloc.0
0x841c  ldloc.0
0x841d  ldarg.1
0x841e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x8423  brfalse.s loc_8431
0x8425  ldloc.0
0x8426  ldarg.1
0x8427  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Item(void)
0x842c  stloc.1
0x842d  ldc.i4.0
0x842e  stloc.2
0x842f  br.s     loc_847E
0x8431  ldarg.0
0x8432  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x8437  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::GetWaitingOperationsMapping()
0x843c  stloc.3
0x843d  ldloc.3
0x843e  ldarg.1
0x843f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x8444  brfalse.s loc_8452
0x8446  ldloc.3
0x8447  ldarg.1
0x8448  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Item(void)
0x844d  stloc.1
0x844e  ldc.i4.2
0x844f  stloc.2
0x8450  br.s     loc_847E
0x8452  ldarg.0
0x8453  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x8458  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager::GetOutstandingOperationsMapping()
0x845d  stloc.s  4
0x845f  ldloc.s  4
0x8461  ldarg.1
0x8462  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x8467  brfalse.s loc_8476
0x8469  ldloc.s  4
0x846b  ldarg.1
0x846c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Item(void)
0x8471  stloc.1
0x8472  ldc.i4.1
0x8473  stloc.2
0x8474  br.s     loc_847E
0x8476  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x847b  stloc.1
0x847c  ldc.i4.3
0x847d  stloc.2
0x847e  ldloc.1
0x847f  ldloc.2
0x8480  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventOperationQueueState>::.ctor(var<u1>, !!T0)
0x8485  ret
```
