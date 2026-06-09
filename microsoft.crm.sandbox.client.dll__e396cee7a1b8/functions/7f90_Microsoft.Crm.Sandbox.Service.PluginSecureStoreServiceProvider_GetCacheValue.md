# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetCacheValue

- ea: `0x7f90`
- end: `0x808d`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::GetCacheValue`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xc0`
- `0x290`
- `0x7f90`

## string_xrefs

- `0x7f90`: `PluginSecureStoreServiceProvider_`
- `0x7fdd`: `PluginSecureStoreServiceProvider.GetCacheValue - cache hit for key {0}`
- `0x7ffb`: `PluginSecureStoreServiceProvider.GetCacheValue - cache miss for key {0}`
- `0x801d`: `cacheValue`
- `0x806e`: `PluginSecureStoreServiceProvider.GetCacheValue - Added cache for key {0} expiring {1}`

## pseudocode

```c

```

## disassembly

```asm
0x7f90  ldstr    aPluginsecurest_21// "PluginSecureStoreServiceProvider_"
0x7f95  call     class Microsoft.Crm.Sandbox.SandboxCallManager Microsoft.Crm.Sandbox.SandboxCallManager::get_Instance()
0x7f9a  ldarg.1
0x7f9b  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x7fa0  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x7fa5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxCallManager::GetCallbackAssemblyId(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo sandboxCallInfo)
0x7faa  box      [mscorlib]System.Guid
0x7faf  ldarg.3
0x7fb0  call     string [mscorlib]System.String::Concat(object, object, object)
0x7fb5  stloc.0
0x7fb6  call     class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache [System.Runtime.Caching]System.Runtime.Caching.MemoryCache::get_Default()
0x7fbb  ldloc.0
0x7fbc  ldnull
0x7fbd  callvirt instance object [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::Get(string, string)
0x7fc2  isinst   mvar<u1>
0x7fc7  unbox.any mvar<u1>
0x7fcc  stloc.1
0x7fcd  ldloc.1
0x7fce  box      mvar<u1>
0x7fd3  brfalse.s loc_7FF3
0x7fd5  ldarg.2
0x7fd6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7fdb  ldc.i4.s 0x1F
0x7fdd  ldstr    aPluginsecurest_22// "PluginSecureStoreServiceProvider.GetCac"...
0x7fe2  ldc.i4.1
0x7fe3  newarr   [mscorlib]System.Object
0x7fe8  dup
0x7fe9  ldc.i4.0
0x7fea  ldloc.0
0x7feb  stelem.ref
0x7fec  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7ff1  ldloc.1
0x7ff2  ret
0x7ff3  ldarg.2
0x7ff4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x7ff9  ldc.i4.s 0x1F
0x7ffb  ldstr    aPluginsecurest_23// "PluginSecureStoreServiceProvider.GetCac"...
0x8000  ldc.i4.1
0x8001  newarr   [mscorlib]System.Object
0x8006  dup
0x8007  ldc.i4.0
0x8008  ldloc.0
0x8009  stelem.ref
0x800a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x800f  ldarg.s  4
0x8011  callvirt instance var<u1> class [mscorlib]System.Func`1<mvar<u1>>::Invoke()
0x8016  stloc.1
0x8017  ldloc.1
0x8018  box      mvar<u1>
0x801d  ldstr    aCachevalue// "cacheValue"
0x8022  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8027  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x802c  stloc.3
0x802d  ldloca.s 3
0x802f  ldc.r8   300.0
0x8038  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0x803d  stloc.2
0x803e  call     class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache [System.Runtime.Caching]System.Runtime.Caching.MemoryCache::get_Default()
0x8043  ldloc.0
0x8044  ldloc.1
0x8045  box      mvar<u1>
0x804a  newobj   instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItem::.ctor(string, object)
0x804f  newobj   instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::.ctor()
0x8054  dup
0x8055  ldloc.2
0x8056  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0x805b  callvirt instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::set_AbsoluteExpiration(valuetype [mscorlib]System.DateTimeOffset)
0x8060  callvirt instance bool [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::Add(class [System.Runtime.Caching]System.Runtime.Caching.CacheItem, class [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy)
0x8065  pop
0x8066  ldarg.2
0x8067  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x806c  ldc.i4.s 0x1F
0x806e  ldstr    aPluginsecurest_24// "PluginSecureStoreServiceProvider.GetCac"...
0x8073  ldc.i4.2
0x8074  newarr   [mscorlib]System.Object
0x8079  dup
0x807a  ldc.i4.0
0x807b  ldloc.0
0x807c  stelem.ref
0x807d  dup
0x807e  ldc.i4.1
0x807f  ldloc.2
0x8080  box      [mscorlib]System.DateTime
0x8085  stelem.ref
0x8086  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x808b  ldloc.1
0x808c  ret
```
