# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::<DetectLongLockedEvents>b__16_1

- ea: `0x4520`
- end: `0x4555`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::<DetectLongLockedEvents>b__16_1`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x4520`
- `0x4bb0`
- `0x60c0`
- `0xd5a0`

## pseudocode

```c

```

## disassembly

```asm
0x4520  ldarg.1
0x4521  ldlen
0x4522  conv.i4
0x4523  ldc.i4.1
0x4524  bge.s    loc_4531
0x4526  ldarg.1
0x4527  ldc.i4.0
0x4528  ldelem.ref
0x4529  isinst   [mscorlib]System.Guid
0x452e  brtrue.s loc_4531
0x4530  ret
0x4531  ldarg.0
0x4532  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x4537  callvirt instance class Microsoft.Crm.Asynchronous.LostEventTracker Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_LostEventTracker()
0x453c  ldarg.0
0x453d  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x4542  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x4547  ldarg.1
0x4548  ldc.i4.0
0x4549  ldelem.ref
0x454a  unbox.any [mscorlib]System.Guid
0x454f  callvirt instance void Microsoft.Crm.Asynchronous.LostEventTracker::Add(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid eventId)
0x4554  ret
```
