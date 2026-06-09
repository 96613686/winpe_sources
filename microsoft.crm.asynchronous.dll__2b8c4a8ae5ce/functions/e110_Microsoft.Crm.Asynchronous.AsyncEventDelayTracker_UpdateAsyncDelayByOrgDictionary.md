# Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::UpdateAsyncDelayByOrgDictionary

- ea: `0xe110`
- end: `0xe142`
- name: `Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::UpdateAsyncDelayByOrgDictionary`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa140`

## callees

- `0xdc30`
- `0xdde0`
- `0xe110`
- `0x121e0`

## pseudocode

```c

```

## disassembly

```asm
0xe110  ldarg.1
0xe111  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0xe116  stloc.0
0xe117  ldarg.0
0xe118  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.AsyncEventDelayTracker>>::get_Value()
0xe11d  stloc.1
0xe11e  ldloc.1
0xe11f  ldloc.0
0xe120  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.AsyncEventDelayTracker>::ContainsKey(var<u1>)
0xe125  brtrue.s loc_E134
0xe127  ldloc.1
0xe128  ldloc.0
0xe129  ldarg.2
0xe12a  newobj   instance void Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::.ctor(string queueName)
0xe12f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.AsyncEventDelayTracker>::Add(var<u1>, !!T0)
0xe134  ldloc.1
0xe135  ldloc.0
0xe136  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.AsyncEventDelayTracker>::get_Item(void)
0xe13b  ldarg.1
0xe13c  callvirt instance void Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::UpdateAsyncDelay(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0xe141  ret
```
