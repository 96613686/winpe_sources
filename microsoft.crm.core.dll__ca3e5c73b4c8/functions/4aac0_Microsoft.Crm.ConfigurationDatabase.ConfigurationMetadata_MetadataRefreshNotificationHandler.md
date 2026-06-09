# Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::MetadataRefreshNotificationHandler

- ea: `0x4aac0`
- end: `0x4ab33`
- name: `Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::MetadataRefreshNotificationHandler`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1f4b0`
- `0x4aac0`

## string_xrefs

- `0x4aaef`: `Queuing work item thread to load cache.`
- `0x4ab27`: `Metadata refresh is pending.  pending cache refresh will pick this up.`

## pseudocode

```c

```

## disassembly

```asm
0x4aac0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4aac5  ldc.i4.s 0x30
0x4aac7  ldstr    aReceivedMetare// "Received MetaRefresh notification.  Eve"...
0x4aacc  ldc.i4.1
0x4aacd  newarr   [mscorlib]System.Object
0x4aad2  dup
0x4aad3  ldc.i4.0
0x4aad4  ldarg.0
0x4aad5  stelem.ref
0x4aad6  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x4aadb  ldsflda  int32 Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::_refreshPending
0x4aae0  ldc.i4.1
0x4aae1  call     int32 [mscorlib]System.Threading.Interlocked::Exchange(int32&, int32)
0x4aae6  brtrue.s loc_4AB13
0x4aae8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4aaed  ldc.i4.s 0x30
0x4aaef  ldstr    aQueuingWorkIte// "Queuing work item thread to load cache."
0x4aaf4  ldc.i4.0
0x4aaf5  newarr   [mscorlib]System.Object
0x4aafa  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x4aaff  ldnull
0x4ab00  ldftn    void Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::MetadataRefresh(object args)
0x4ab06  newobj   instance void [mscorlib]System.Threading.WaitCallback::.ctor(object, native int)
0x4ab0b  ldarg.0
0x4ab0c  call     bool [mscorlib]System.Threading.ThreadPool::QueueUserWorkItem(class [mscorlib]System.Threading.WaitCallback, object)
0x4ab11  pop
0x4ab12  ret
0x4ab13  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4ab18  ldc.i4.s 0x30
0x4ab1a  ldstr    a0// "{0}"
0x4ab1f  ldc.i4.1
0x4ab20  newarr   [mscorlib]System.Object
0x4ab25  dup
0x4ab26  ldc.i4.0
0x4ab27  ldstr    aMetadataRefres// "Metadata refresh is pending.  pending c"...
0x4ab2c  stelem.ref
0x4ab2d  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x4ab32  ret
```
