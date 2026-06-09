# Microsoft.Crm.Sandbox.SandboxHostManager::WritePluginTraceLog

- ea: `0x1930`
- end: `0x1a78`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::WritePluginTraceLog`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1930`
- `0x63d0`
- `0x6420`
- `0x6610`
- `0x6650`

## string_xrefs

- `0x1999`: `PluginTraceLog.OutboundQueueSize`
- `0x19b0`: `PluginTraceLog.OrganizationCount`
- `0x19ee`: `SandboxHostManager.WritePluginTraceLog: {0}`
- `0x1a67`: `SandboxHostManager.WritePluginTraceLog: Exiting WritePluginTraceLog`

## pseudocode

```c

```

## disassembly

```asm
0x1930  ldarg.0
0x1931  ldnull
0x1932  ceq
0x1934  ldstr    aStateobjectNot// "stateObject not null"
0x1939  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x193e  ldsfld   bool Microsoft.Crm.Sandbox.SandboxHostManager::_processingWritePluginTraceLog
0x1943  brfalse.s loc_1946
0x1945  ret
0x1946  ldsfld   object Microsoft.Crm.Sandbox.SandboxHostManager::_processingLock
0x194b  stloc.0
0x194c  ldc.i4.0
0x194d  stloc.1
0x194e  ldloc.0
0x194f  ldloca.s 1
0x1951  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1956  ldsfld   bool Microsoft.Crm.Sandbox.SandboxHostManager::_processingWritePluginTraceLog
0x195b  brfalse.s loc_1962
0x195d  leave    loc_1A77
0x1962  ldc.i4.1
0x1963  stsfld   bool Microsoft.Crm.Sandbox.SandboxHostManager::_processingWritePluginTraceLog
0x1968  leave.s  loc_1974
0x196a  ldloc.1
0x196b  brfalse.s loc_1973
0x196d  ldloc.0
0x196e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1973  endfinally
0x1974  nop
0x1975  call     class Microsoft.Crm.Sandbox.IPluginTraceLogQueuesManager Microsoft.Crm.Sandbox.PluginTraceLogQueuesManager::get_Instance()
0x197a  callvirt instance class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>, int32> Microsoft.Crm.Sandbox.IPluginTraceLogQueuesManager::SwapInboundAndOutboundQueues()
0x197f  stloc.2
0x1980  ldloc.2
0x1981  brfalse.s loc_19E3
0x1983  ldloc.2
0x1984  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>, int32>::get_Item1()
0x1989  brfalse.s loc_19E3
0x198b  ldloc.2
0x198c  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>, int32>::get_Item2()
0x1991  ldc.i4.0
0x1992  ble.s    loc_19E3
0x1994  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_Instance()
0x1999  ldstr    aPlugintracelog_0// "PluginTraceLog.OutboundQueueSize"
0x199e  ldloc.2
0x199f  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>, int32>::get_Item2()
0x19a4  ldnull
0x19a5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.Metric [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::AddMetric(string, int32, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x19aa  pop
0x19ab  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_Instance()
0x19b0  ldstr    aPlugintracelog_1// "PluginTraceLog.OrganizationCount"
0x19b5  ldloc.2
0x19b6  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>, int32>::get_Item1()
0x19bb  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>::get_Keys()
0x19c0  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x19c5  ldnull
0x19c6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.Metric [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::AddMetric(string, int32, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x19cb  pop
0x19cc  ldloc.2
0x19cd  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>, int32>::get_Item1()
0x19d2  ldloc.2
0x19d3  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>, int32>::get_Item2()
0x19d8  newobj   instance void Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::.ctor(class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> queues, int32 queueSize)
0x19dd  callvirt instance class [mscorlib]System.Threading.CancellationTokenSource Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::StartProcessingPluginTraceLogQueues()
0x19e2  pop
0x19e3  leave.s  loc_1A3E
0x19e5  stloc.3
0x19e6  ldloc.3
0x19e7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19ec  ldc.i4.s 0x26
0x19ee  ldstr    aSandboxhostman_40// "SandboxHostManager.WritePluginTraceLog:"...
0x19f3  ldc.i4.1
0x19f4  newarr   [mscorlib]System.Object
0x19f9  dup
0x19fa  ldc.i4.0
0x19fb  ldloc.3
0x19fc  stelem.ref
0x19fd  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a02  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x1a07  stloc.s  4
0x1a09  ldloc.s  4
0x1a0b  ldstr    aMscrmsandboxcl// "MSCRMSandboxClient"
0x1a10  ldc.i4.1
0x1a11  ldc.i4   0xC0004F20
0x1a16  conv.u8
0x1a17  ldc.i4.2
0x1a18  newarr   [mscorlib]System.Object
0x1a1d  dup
0x1a1e  ldc.i4.0
0x1a1f  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x1a24  stelem.ref
0x1a25  dup
0x1a26  ldc.i4.1
0x1a27  ldloc.3
0x1a28  stelem.ref
0x1a29  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x1a2e  leave.s  loc_1A3C
0x1a30  ldloc.s  4
0x1a32  brfalse.s loc_1A3B
0x1a34  ldloc.s  4
0x1a36  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a3b  endfinally
0x1a3c  leave.s  loc_1A3E
0x1a3e  ldsfld   object Microsoft.Crm.Sandbox.SandboxHostManager::_processingLock
0x1a43  stloc.0
0x1a44  ldc.i4.0
0x1a45  stloc.1
0x1a46  ldloc.0
0x1a47  ldloca.s 1
0x1a49  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1a4e  ldc.i4.0
0x1a4f  stsfld   bool Microsoft.Crm.Sandbox.SandboxHostManager::_processingWritePluginTraceLog
0x1a54  leave.s  loc_1A60
0x1a56  ldloc.1
0x1a57  brfalse.s loc_1A5F
0x1a59  ldloc.0
0x1a5a  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1a5f  endfinally
0x1a60  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a65  ldc.i4.s 0x21
0x1a67  ldstr    aSandboxhostman_41// "SandboxHostManager.WritePluginTraceLog:"...
0x1a6c  ldc.i4.0
0x1a6d  newarr   [mscorlib]System.Object
0x1a72  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a77  ret
```
