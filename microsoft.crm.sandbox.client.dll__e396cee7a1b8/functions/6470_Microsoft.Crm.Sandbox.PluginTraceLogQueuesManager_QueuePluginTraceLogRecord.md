# Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::QueuePluginTraceLogRecord

- ea: `0x6470`
- end: `0x6597`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::QueuePluginTraceLogRecord`
- size: `295`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x3810`
- `0x6470`
- `0x65a0`
- `0x65b0`
- `0x65c0`
- `0x65d0`

## string_xrefs

- `0x6471`: `pluginTraceLogRecord`
- `0x6514`: `PluginTraceLogQueuesManager.QueuePluginTraceLogRecord: Some plug-in trace logs have been discarded because the system is too busy. TotalInboundQueueRecordCount: {0}; OrgRecordCount : {1}; OrgReservedCount: {2}; OrgMaxSizeCount: {3}; PluginTraceLogSizeToAcceptBeyondOrgReserved: {4}; OrganizationId: {5};`
- `0x6589`: `PluginTraceLog.InboundQueueSizeExceeded`

## pseudocode

```c

```

## disassembly

```asm
0x6470  ldarg.1
0x6471  ldstr    aPlugintracelog_3// "pluginTraceLogRecord"
0x6476  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x647b  ldarg.1
0x647c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OrganizationId()
0x6481  call     bool Microsoft.Crm.Sandbox.SandboxPluginHelper::IsPluginTracingFeatureEnabledForOrg(valuetype [mscorlib]System.Guid organizationId)
0x6486  brtrue.s loc_6489
0x6488  ret
0x6489  ldnull
0x648a  stloc.0
0x648b  ldarg.0
0x648c  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_inboundQueues
0x6491  ldarg.1
0x6492  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OrganizationId()
0x6497  ldloca.s 0
0x6499  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>::TryGetValue(var<u1>, !!T0)
0x649e  brtrue.s loc_64B7
0x64a0  ldarg.0
0x64a1  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_inboundQueues
0x64a6  ldarg.1
0x64a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OrganizationId()
0x64ac  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>::.ctor()
0x64b1  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>::GetOrAdd(void, var<u1>)
0x64b6  stloc.0
0x64b7  ldsfld   int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_totalInboundQueueRecordCount
0x64bc  call     int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::get_PluginTraceLogMaxQueueSizeBeforeStoppingEnqueue()
0x64c1  bge.s    loc_650C
0x64c3  ldloc.0
0x64c4  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>::get_Count()
0x64c9  call     int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::get_ReservedPluginTraceLogCountPerOrg()
0x64ce  blt.s    loc_64E9
0x64d0  ldloc.0
0x64d1  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>::get_Count()
0x64d6  call     int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::get_MaxPluginTraceLogCountPerOrg()
0x64db  bge.s    loc_650C
0x64dd  ldsfld   int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_totalInboundQueueRecordCount
0x64e2  call     int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::get_PluginTraceLogSizeToAcceptBeyondOrgReserved()
0x64e7  bge.s    loc_650C
0x64e9  ldarg.0
0x64ea  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_inboundQueues
0x64ef  ldarg.1
0x64f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OrganizationId()
0x64f5  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>::get_Item(void)
0x64fa  ldarg.1
0x64fb  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>::Enqueue(var<u1>)
0x6500  ldsflda  int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_totalInboundQueueRecordCount
0x6505  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x650a  pop
0x650b  ret
0x650c  ldarg.1
0x650d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OrganizationId()
0x6512  ldc.i4.s 0x28
0x6514  ldstr    aPlugintracelog_4// "PluginTraceLogQueuesManager.QueuePlugin"...
0x6519  ldc.i4.6
0x651a  newarr   [mscorlib]System.Object
0x651f  dup
0x6520  ldc.i4.0
0x6521  ldsfld   int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_totalInboundQueueRecordCount
0x6526  box      [mscorlib]System.Int32
0x652b  stelem.ref
0x652c  dup
0x652d  ldc.i4.1
0x652e  ldarg.0
0x652f  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::_inboundQueues
0x6534  ldarg.1
0x6535  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OrganizationId()
0x653a  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>::get_Item(void)
0x653f  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>::get_Count()
0x6544  box      [mscorlib]System.Int32
0x6549  stelem.ref
0x654a  dup
0x654b  ldc.i4.2
0x654c  call     int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::get_ReservedPluginTraceLogCountPerOrg()
0x6551  box      [mscorlib]System.Int32
0x6556  stelem.ref
0x6557  dup
0x6558  ldc.i4.3
0x6559  call     int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::get_MaxPluginTraceLogCountPerOrg()
0x655e  box      [mscorlib]System.Int32
0x6563  stelem.ref
0x6564  dup
0x6565  ldc.i4.4
0x6566  call     int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::get_PluginTraceLogSizeToAcceptBeyondOrgReserved()
0x656b  box      [mscorlib]System.Int32
0x6570  stelem.ref
0x6571  dup
0x6572  ldc.i4.5
0x6573  ldarg.1
0x6574  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OrganizationId()
0x6579  box      [mscorlib]System.Guid
0x657e  stelem.ref
0x657f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6584  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_Instance()
0x6589  ldstr    aPlugintracelog_5// "PluginTraceLog.InboundQueueSizeExceeded"
0x658e  ldc.i4.1
0x658f  ldnull
0x6590  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.Metric [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::AddMetric(string, int32, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x6595  pop
0x6596  ret
```
