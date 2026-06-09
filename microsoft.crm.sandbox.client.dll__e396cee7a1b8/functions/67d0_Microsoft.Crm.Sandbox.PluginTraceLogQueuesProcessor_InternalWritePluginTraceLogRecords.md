# Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::InternalWritePluginTraceLogRecords

- ea: `0x67d0`
- end: `0x6918`
- name: `Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::InternalWritePluginTraceLogRecords`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x67a0`

## callees

- `0x67d0`
- `0x6920`
- `0x69a0`
- `0x6a50`

## string_xrefs

- `0x68a1`: `PluginTraceLog.RecordLostAfterMaxRetries`
- `0x68b8`: `InternalWritePluginTraceLogRecords: Error encountered while writing plugin trace log record and the record was discarded after max retries: {0}`
- `0x68d8`: `PluginTraceLog.RecordLostWithoutRetry`
- `0x68ef`: `InternalWritePluginTraceLogRecords: Error encountered while writing plugin trace log record and the record was discarded without retry: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x67d0  ldnull
0x67d1  stloc.0
0x67d2  ldnull
0x67d3  stloc.1
0x67d4  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IPluginTraceLogService [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PluginTraceLogService::NewService()
0x67d9  stloc.2
0x67da  br       loc_690A
0x67df  ldarga.s 1
0x67e1  call     instance bool [mscorlib]System.Threading.CancellationToken::get_IsCancellationRequested()
0x67e6  brfalse.s loc_67E9
0x67e8  ret
0x67e9  ldloc.0
0x67ea  ldloca.s 1
0x67ec  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>::TryDequeue(var<u1>&)
0x67f1  pop
0x67f2  ldloc.1
0x67f3  brfalse  loc_690A
0x67f8  ldloc.1
0x67f9  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_WrittenToStorage()
0x67fe  brtrue   loc_690A
0x6803  ldloc.1
0x6804  newobj   instance void Microsoft.Crm.Sandbox.PluginTraceLogWriter::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord pluginTraceLogRecord)
0x6809  stloc.3
0x680a  ldloc.2
0x680b  ldloc.1
0x680c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OrganizationId()
0x6811  ldloc.3
0x6812  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IPluginTraceLogService::Write(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IPluginTraceLogWriter)
0x6817  leave    loc_690A
0x681c  stloc.s  4
0x681e  ldloc.1
0x681f  ldc.i4.5
0x6820  newarr   [mscorlib]System.Object
0x6825  dup
0x6826  ldc.i4.0
0x6827  ldloc.1
0x6828  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_PluginTypeName()
0x682d  stelem.ref
0x682e  dup
0x682f  ldc.i4.1
0x6830  ldstr    asc_F6C4// "; "
0x6835  stelem.ref
0x6836  dup
0x6837  ldc.i4.2
0x6838  ldloc.s  4
0x683a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x683f  stelem.ref
0x6840  dup
0x6841  ldc.i4.3
0x6842  ldstr    asc_F6C4// "; "
0x6847  stelem.ref
0x6848  dup
0x6849  ldc.i4.4
0x684a  ldloc.s  4
0x684c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6851  stelem.ref
0x6852  call     string [mscorlib]System.String::Concat(object[])
0x6857  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_LastErrorMessage(string)
0x685c  ldloc.1
0x685d  dup
0x685e  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_WriteAttempts()
0x6863  stloc.s  5
0x6865  ldloc.s  5
0x6867  ldc.i4.1
0x6868  add
0x6869  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::set_WriteAttempts(int32)
0x686e  ldarg.0
0x686f  ldfld    bool Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_retryWhileProcessingQueues
0x6874  brfalse.s loc_68D3
0x6876  ldloc.1
0x6877  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_WriteAttempts()
0x687c  call     int32 Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::get_PluginTraceLogRecordMaxRetryCount()
0x6881  bgt.s    loc_689C
0x6883  ldarg.0
0x6884  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>> Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::_queues
0x6889  ldloc.1
0x688a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OrganizationId()
0x688f  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>>::get_Item(void)
0x6894  ldloc.1
0x6895  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>::Enqueue(var<u1>)
0x689a  br.s     loc_6908
0x689c  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_Instance()
0x68a1  ldstr    aPlugintracelog_9// "PluginTraceLog.RecordLostAfterMaxRetrie"...
0x68a6  ldc.i4.1
0x68a7  ldnull
0x68a8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.Metric [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::AddMetric(string, int32, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x68ad  pop
0x68ae  ldloc.s  4
0x68b0  ldloc.1
0x68b1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OrganizationId()
0x68b6  ldc.i4.s 0x28
0x68b8  ldstr    aInternalwritep// "InternalWritePluginTraceLogRecords: Err"...
0x68bd  ldc.i4.1
0x68be  newarr   [mscorlib]System.Object
0x68c3  dup
0x68c4  ldc.i4.0
0x68c5  ldloc.1
0x68c6  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_LastErrorMessage()
0x68cb  stelem.ref
0x68cc  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x68d1  br.s     loc_6908
0x68d3  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_Instance()
0x68d8  ldstr    aPlugintracelog_10// "PluginTraceLog.RecordLostWithoutRetry"
0x68dd  ldc.i4.1
0x68de  ldnull
0x68df  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.Metric [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::AddMetric(string, int32, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x68e4  pop
0x68e5  ldloc.s  4
0x68e7  ldloc.1
0x68e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_OrganizationId()
0x68ed  ldc.i4.s 0x28
0x68ef  ldstr    aInternalwritep_0// "InternalWritePluginTraceLogRecords: Err"...
0x68f4  ldc.i4.1
0x68f5  newarr   [mscorlib]System.Object
0x68fa  dup
0x68fb  ldc.i4.0
0x68fc  ldloc.1
0x68fd  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord::get_LastErrorMessage()
0x6902  stelem.ref
0x6903  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6908  leave.s  loc_690A
0x690a  ldarg.0
0x690b  ldloca.s 0
0x690d  call     instance bool Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::TryGetNextQueue([out] class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.PluginTraceLogRecord>& nextQueue)
0x6912  brtrue   loc_67DF
0x6917  ret
```
