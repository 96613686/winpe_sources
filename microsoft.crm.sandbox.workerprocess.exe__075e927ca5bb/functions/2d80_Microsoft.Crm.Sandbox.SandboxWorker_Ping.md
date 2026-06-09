# Microsoft.Crm.Sandbox.SandboxWorker::Ping

- ea: `0x2d80`
- end: `0x2f22`
- name: `Microsoft.Crm.Sandbox.SandboxWorker::Ping`
- size: `418`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x2d80`
- `0x2f30`
- `0x3a10`

## string_xrefs

- `0x2ec3`: `SandboxWorker.Ping:Thread[{0:d4}]: Spent {1} ms in Ping in the Worker`

## pseudocode

```c

```

## disassembly

```asm
0x2d80  ldstr    aSandboxworkerP// "SandboxWorker.Ping"
0x2d85  ldarg.1
0x2d86  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_OrgTraceCategory()
0x2d8b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2d90  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2d95  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2d9a  ldarg.1
0x2d9b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x2da0  ldarg.1
0x2da1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ActivityId()
0x2da6  stloc.1
0x2da7  ldloca.s 1
0x2da9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x2dae  ldc.i4.0
0x2daf  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32)
0x2db4  stloc.0
0x2db5  ldstr    aIsandboxworker// "ISandboxWorker.Ping"
0x2dba  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::.ctor(string)
0x2dbf  stloc.2
0x2dc0  ldarg.1
0x2dc1  ldstr    aSandboxworkerP// "SandboxWorker.Ping"
0x2dc6  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::set_PluginInfo(string)
0x2dcb  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x2dd0  stloc.3
0x2dd1  ldarg.1
0x2dd2  ldstr    aCallinfo// "callInfo"
0x2dd7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2ddc  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorker::_pingCount
0x2de1  stloc.s  4
0x2de3  ldloc.s  4
0x2de5  ldc.i4.3
0x2de6  bge.s    loc_2E1E
0x2de8  ldarg.1
0x2de9  ldstr    aIsandboxworker_0// "ISandboxWorker.Ping: "
0x2dee  ldloc.s  4
0x2df0  box      [mscorlib]System.Int32
0x2df5  call     string [mscorlib]System.String::Concat(object, object)
0x2dfa  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::Trace(string)
0x2dff  ldloc.2
0x2e00  ldstr    aIsandboxworker_0// "ISandboxWorker.Ping: "
0x2e05  ldloc.s  4
0x2e07  box      [mscorlib]System.Int32
0x2e0c  call     string [mscorlib]System.String::Concat(object, object)
0x2e11  ldarg.1
0x2e12  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x2e17  ldarg.1
0x2e18  ldc.i4.0
0x2e19  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::Enter(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, int32)
0x2e1e  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxWorker::_pingCount
0x2e23  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x2e28  pop
0x2e29  ldarg.2
0x2e2a  brfalse.s loc_2E41
0x2e2c  ldarg.2
0x2e2d  stsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxWorker::_workerConfiguration
0x2e32  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter Microsoft.Crm.Sandbox.SandboxWorker::_exceptionConverter
0x2e37  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxWorker::_workerConfiguration
0x2e3c  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter::Update(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration)
0x2e41  ldarg.s  4
0x2e43  brfalse.s loc_2E4C
0x2e45  ldarg.s  4
0x2e47  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Sandbox.SandboxWorker::_sandboxAdditionalInfo
0x2e4c  ldarg.3
0x2e4d  brfalse.s loc_2E9F
0x2e4f  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxWorker::_remoteSettings
0x2e54  brfalse.s loc_2E63
0x2e56  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxWorker::_remoteSettings
0x2e5b  ldarg.3
0x2e5c  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings::Updated(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings)
0x2e61  brfalse.s loc_2E9F
0x2e63  ldarg.3
0x2e64  stsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxWorker::_remoteSettings
0x2e69  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxWorker::_remoteSettings
0x2e6e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings::ResetTrace()
0x2e73  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxWorker::_remoteSettings
0x2e78  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings::get_TraceCategories()
0x2e7d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e82  brtrue.s loc_2E9F
0x2e84  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxWorker::_remoteSettings
0x2e89  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings::get_TraceEnabled()
0x2e8e  brfalse.s loc_2E9F
0x2e90  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxWorker::_remoteSettings
0x2e95  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings::get_TraceCategories()
0x2e9a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::set_TraceCategories(string)
0x2e9f  ldloc.s  4
0x2ea1  ldc.i4.3
0x2ea2  bge.s    loc_2EAA
0x2ea4  ldloc.2
0x2ea5  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::GoodExit()
0x2eaa  call     bool Microsoft.Crm.Sandbox.SandboxWorker::get_Shutdown()
0x2eaf  brfalse.s loc_2EB6
0x2eb1  ldc.i4.5
0x2eb2  stloc.s  5
0x2eb4  leave.s  loc_2F1F
0x2eb6  ldloc.3
0x2eb7  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x2ebc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2ec1  ldc.i4.s 0x21
0x2ec3  ldstr    aSandboxworkerP_0// "SandboxWorker.Ping:Thread[{0:d4}]: Spen"...
0x2ec8  ldc.i4.2
0x2ec9  newarr   [mscorlib]System.Object
0x2ece  dup
0x2ecf  ldc.i4.0
0x2ed0  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2ed5  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x2eda  box      [mscorlib]System.Int32
0x2edf  stelem.ref
0x2ee0  dup
0x2ee1  ldc.i4.1
0x2ee2  ldloc.3
0x2ee3  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x2ee8  stloc.s  6
0x2eea  ldloca.s 6
0x2eec  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x2ef1  box      [mscorlib]System.Double
0x2ef6  stelem.ref
0x2ef7  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2efc  ldc.i4.3
0x2efd  stloc.s  5
0x2eff  leave.s  loc_2F1F
0x2f01  stloc.s  7
0x2f03  ldarg.0
0x2f04  ldloc.s  7
0x2f06  ldloc.2
0x2f07  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2f0c  ldarg.1
0x2f0d  ldc.i4.1
0x2f0e  call     instance void Microsoft.Crm.Sandbox.SandboxWorker::HandleException(class [mscorlib]System.Exception e, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker tracker, valuetype [mscorlib]System.Guid orgId, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, bool exceptionRetriable)
0x2f13  rethrow
0x2f15  ldloc.0
0x2f16  brfalse.s loc_2F1E
0x2f18  ldloc.0
0x2f19  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f1e  endfinally
0x2f1f  ldloc.s  5
0x2f21  ret
```
