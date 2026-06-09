# Microsoft.Crm.Asynchronous.ServiceTracker::.ctor

- ea: `0xf300`
- end: `0xf358`
- name: `Microsoft.Crm.Asynchronous.ServiceTracker::.ctor`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x17d40`

## callees

- `0x7550`
- `0x75b0`
- `0xf410`

## pseudocode

```c

```

## disassembly

```asm
0xf300  ldarg.0
0xf301  ldc.i4.0
0xf302  newobj   instance void [mscorlib]System.Threading.ManualResetEventSlim::.ctor(bool)
0xf307  stfld    class [mscorlib]System.Threading.ManualResetEventSlim Microsoft.Crm.Asynchronous.ServiceTracker::_initializationCompletedEvent
0xf30c  ldarg.0
0xf30d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::.ctor()
0xf312  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData> Microsoft.Crm.Asynchronous.ServiceTracker::_services
0xf317  ldarg.0
0xf318  call     instance void [mscorlib]System.Object::.ctor()
0xf31d  ldarg.1
0xf31e  ldstr    aIserverfilter// "IServerFilter"
0xf323  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xf328  ldarg.0
0xf329  ldarg.1
0xf32a  stfld    class Microsoft.Crm.Asynchronous.IServerFilter Microsoft.Crm.Asynchronous.ServiceTracker::_serverFilter
0xf32f  call     class Microsoft.Crm.Asynchronous.AsyncServerCache Microsoft.Crm.Asynchronous.AsyncServerCache::get_Instance()
0xf334  ldarg.0
0xf335  ldftn    instance void Microsoft.Crm.Asynchronous.ServiceTracker::OnServicesChanged(object sender, class [mscorlib]System.EventArgs args)
0xf33b  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xf340  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServerCache::add_CacheUpdated(class [mscorlib]System.EventHandler value)
0xf345  ldarg.0
0xf346  call     instance bool Microsoft.Crm.Asynchronous.ServiceTracker::GetRelevantServersFromCache()
0xf34b  pop
0xf34c  ldarg.0
0xf34d  ldfld    class [mscorlib]System.Threading.ManualResetEventSlim Microsoft.Crm.Asynchronous.ServiceTracker::_initializationCompletedEvent
0xf352  callvirt instance void [mscorlib]System.Threading.ManualResetEventSlim::Set()
0xf357  ret
```
