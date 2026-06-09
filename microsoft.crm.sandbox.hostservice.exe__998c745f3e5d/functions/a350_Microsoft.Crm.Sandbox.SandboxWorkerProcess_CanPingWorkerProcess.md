# Microsoft.Crm.Sandbox.SandboxWorkerProcess::CanPingWorkerProcess

- ea: `0xa350`
- end: `0xa7de`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::CanPingWorkerProcess`
- size: `1166`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0xa0f0`
- `0xcd60`

## callees

- `0x48e0`
- `0x4900`
- `0x4920`
- `0x4930`
- `0x5770`
- `0x5780`
- `0x5790`
- `0x57b0`
- `0x57c0`
- `0x57d0`
- `0x5930`
- `0x9730`
- `0x98f0`
- `0xa350`

## string_xrefs

- `0xa489`: `SandboxWorkerProcess.CanPingWorkerProcess:Thread[{0:d4}]: Spent {1} ms in CanPingWorkerProcess to ping the Execute Channel`
- `0xa51f`: `SandboxWorkerProcess.CanPingWorkerProcess:Thread[{0:d4}]: Spent {1} ms in CanPingWorkerProcess to ping the Ping Channel`
- `0xa5e6`: `SandboxWorkerProcess.CanPingWorkerProcess:Thread[{4:d4}]:Proxy ping failed for worker process:{0}, client id:{1} on channel:{2} with exception: {3}`
- `0xa63c`: `SandboxWorkerProcess.CanPingWorkerProcess:Thread[{4:d4}]:Proxy ping failed for worker process:{0}, client id:{1} on channel:{2} with exception: {3}`
- `0xa698`: `SandboxWorkerProcess.CanPingWorkerProcess:Thread[{4:d4}]:Proxy ping failed for worker process:{0}, client id:{1} on channel:{2} with exception: {3}`
- `0xa6f4`: `SandboxWorkerProcess.CanPingWorkerProcess:Thread[{4:d4}]:Proxy ping failed for worker process:{0}, client id:{1} on channel:{2} with exception: {3}`
- `0xa763`: `SandboxWorkerProcess.CanPingWorkerProcess:Thread[{2:d4}]: Replacing worker client:{0} as client is faulted or not initialized. isClientFaulted:{1}`

## pseudocode

```c

```

## disassembly

```asm
0xa350  ldarg.0
0xa351  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa356  ldc.i4.s 0x21
0xa358  ldstr    aSandboxworkerp_27// "SandboxWorkerProcess.CanPingWorkerProce"...
0xa35d  ldc.i4.0
0xa35e  newarr   [mscorlib]System.Object
0xa363  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa368  ldarg.0
0xa369  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa36e  ldstr    aWorkerclient// "_workerClient"
0xa373  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xa378  ldc.i4.0
0xa379  stloc.0
0xa37a  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xa37f  stloc.1
0xa380  ldloc.1
0xa381  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0xa386  ldarg.0
0xa387  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa38c  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorkerClient::get_LastCall()
0xa391  stloc.s  4
0xa393  ldloca.s 4
0xa395  ldc.r8   5.0
0xa39e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0xa3a3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xa3a8  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xa3ad  stloc.2
0xa3ae  ldstr    aRefreshexecute// "refreshExecuteClient"
0xa3b3  ldloca.s 2
0xa3b5  call     instance string [mscorlib]System.Boolean::ToString()
0xa3ba  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xa3bf  ldstr    aClientid// "ClientId"
0xa3c4  ldarg.0
0xa3c5  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa3ca  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_ClientId()
0xa3cf  callvirt instance string [mscorlib]System.Object::ToString()
0xa3d4  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xa3d9  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xa3de  stloc.3
0xa3df  ldc.i4.1
0xa3e0  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::.ctor(bool)
0xa3e5  stloc.s  5
0xa3e7  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0xa3ec  ldc.i4.s 0x13
0xa3ee  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0xa3f3  stloc.s  6
0xa3f5  ldarg.0
0xa3f6  ldflda   int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_activeWorkerPingCount
0xa3fb  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0xa400  pop
0xa401  ldarg.0
0xa402  ldflda   int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_totalWorkerPingCount
0xa407  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0xa40c  pop
0xa40d  ldloc.2
0xa40e  brfalse  loc_A4C7
0xa413  ldarg.0
0xa414  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa419  ldc.i4.s 0x28
0xa41b  ldstr    aSandboxworkerp_28// "SandboxWorkerProcess.CanPingWorkerProce"...
0xa420  ldc.i4.0
0xa421  newarr   [mscorlib]System.Object
0xa426  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa42b  ldarg.0
0xa42c  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa431  ldc.i4.0
0xa432  ldc.i4.0
0xa433  ldloc.s  6
0xa435  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xa43a  callvirt instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::SetOperationTimeout(valuetype [mscorlib]System.TimeSpan)
0xa43f  ldarg.0
0xa440  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa445  ldarg.0
0xa446  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa44b  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_Proxy()
0xa450  ldloc.s  5
0xa452  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostWorkerConfiguration()
0xa457  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxHost::get_RemoteTraceSettings()
0xa45c  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Sandbox.SandboxHost::get_SandboxAdditionalInfo()
0xa461  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker::Ping(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration, class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>)
0xa466  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus value)
0xa46b  ldarg.0
0xa46c  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa471  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xa476  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_LastCall(valuetype [mscorlib]System.DateTime value)
0xa47b  ldloc.3
0xa47c  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xa481  ldarg.0
0xa482  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa487  ldc.i4.s 0x21
0xa489  ldstr    aSandboxworkerp_29// "SandboxWorkerProcess.CanPingWorkerProce"...
0xa48e  ldc.i4.2
0xa48f  newarr   [mscorlib]System.Object
0xa494  dup
0xa495  ldc.i4.0
0xa496  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xa49b  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xa4a0  box      [mscorlib]System.Int32
0xa4a5  stelem.ref
0xa4a6  dup
0xa4a7  ldc.i4.1
0xa4a8  ldloc.3
0xa4a9  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0xa4ae  stloc.s  7
0xa4b0  ldloca.s 7
0xa4b2  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0xa4b7  box      [mscorlib]System.Double
0xa4bc  stelem.ref
0xa4bd  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa4c2  br       loc_A558
0xa4c7  ldarg.0
0xa4c8  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa4cd  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerClient::get_PingClient()
0xa4d2  ldc.i4.0
0xa4d3  ldc.i4.0
0xa4d4  ldloc.s  6
0xa4d6  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xa4db  callvirt instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::SetOperationTimeout(valuetype [mscorlib]System.TimeSpan)
0xa4e0  ldarg.0
0xa4e1  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa4e6  ldarg.0
0xa4e7  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa4ec  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerClient::get_PingClient()
0xa4f1  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_Proxy()
0xa4f6  ldloc.s  5
0xa4f8  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostWorkerConfiguration()
0xa4fd  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxHost::get_RemoteTraceSettings()
0xa502  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Sandbox.SandboxHost::get_SandboxAdditionalInfo()
0xa507  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker::Ping(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration, class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings, class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>)
0xa50c  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus value)
0xa511  ldloc.3
0xa512  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xa517  ldarg.0
0xa518  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa51d  ldc.i4.s 0x21
0xa51f  ldstr    aSandboxworkerp_30// "SandboxWorkerProcess.CanPingWorkerProce"...
0xa524  ldc.i4.2
0xa525  newarr   [mscorlib]System.Object
0xa52a  dup
0xa52b  ldc.i4.0
0xa52c  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xa531  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xa536  box      [mscorlib]System.Int32
0xa53b  stelem.ref
0xa53c  dup
0xa53d  ldc.i4.1
0xa53e  ldloc.3
0xa53f  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0xa544  stloc.s  7
0xa546  ldloca.s 7
0xa548  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0xa54d  box      [mscorlib]System.Double
0xa552  stelem.ref
0xa553  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa558  ldnull
0xa559  ldarg.0
0xa55a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa55f  ldc.i4.3
0xa560  ldc.i4.s 0x21
0xa562  ldc.i4.0
0xa563  ldc.i4.1
0xa564  ldstr    aSandboxworkerp_31// "SandboxWorkerProcess.CanPingWorkerProce"...
0xa569  ldc.i4.1
0xa56a  newarr   [mscorlib]System.Object
0xa56f  dup
0xa570  ldc.i4.0
0xa571  ldarg.0
0xa572  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa577  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxWorkerClient::get_WorkerStatus()
0xa57c  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus
0xa581  stelem.ref
0xa582  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0xa587  ldarg.0
0xa588  ldflda   int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_activeWorkerPingCount
0xa58d  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0xa592  pop
0xa593  ldarg.0
0xa594  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa599  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxWorkerClient::get_WorkerStatus()
0xa59e  ldc.i4.3
0xa59f  ceq
0xa5a1  stloc.0
0xa5a2  ldloc.0
0xa5a3  ldarg.0
0xa5a4  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa5a9  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxWorkerClient::get_WorkerStatus()
0xa5ae  ldc.i4.5
0xa5af  ceq
0xa5b1  or
0xa5b2  stloc.0
0xa5b3  leave    loc_A7DC
0xa5b8  stloc.s  8
0xa5ba  ldarg.0
0xa5bb  ldflda   int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_activeWorkerPingCount
0xa5c0  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0xa5c5  pop
0xa5c6  ldloc.s  8
0xa5c8  isinst   [System.ServiceModel]System.ServiceModel.CommunicationObjectFaultedException
0xa5cd  ldnull
0xa5ce  cgt.un
0xa5d0  stloc.s  9
0xa5d2  ldloc.s  8
0xa5d4  isinst   [System.ServiceModel]System.ServiceModel.EndpointNotFoundException
0xa5d9  ldnull
0xa5da  cgt.un
0xa5dc  stloc.s  0xA
0xa5de  ldarg.0
0xa5df  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa5e4  ldc.i4.s 0x21
0xa5e6  ldstr    aSandboxworkerp_32// "SandboxWorkerProcess.CanPingWorkerProce"...
0xa5eb  ldc.i4.5
0xa5ec  newarr   [mscorlib]System.Object
0xa5f1  dup
0xa5f2  ldc.i4.0
0xa5f3  ldarg.0
0xa5f4  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xa5f9  stelem.ref
0xa5fa  dup
0xa5fb  ldc.i4.1
0xa5fc  ldarg.0
0xa5fd  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa602  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_ClientId()
0xa607  stelem.ref
0xa608  dup
0xa609  ldc.i4.2
0xa60a  ldloc.2
0xa60b  brtrue.s loc_A614
0xa60d  ldstr    aPingChannel// "Ping Channel"
0xa612  br.s     loc_A619
0xa614  ldstr    aExecuteChannel// "Execute Channel"
0xa619  stelem.ref
0xa61a  dup
0xa61b  ldc.i4.3
0xa61c  ldloc.s  8
0xa61e  stelem.ref
0xa61f  dup
0xa620  ldc.i4.4
0xa621  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xa626  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xa62b  box      [mscorlib]System.Int32
0xa630  stelem.ref
0xa631  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa636  ldarg.0
0xa637  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxWorkerProcess::Logger
0xa63c  ldstr    aSandboxworkerp_32// "SandboxWorkerProcess.CanPingWorkerProce"...
0xa641  ldc.i4.5
0xa642  newarr   [mscorlib]System.Object
0xa647  dup
0xa648  ldc.i4.0
0xa649  ldarg.0
0xa64a  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xa64f  stelem.ref
0xa650  dup
0xa651  ldc.i4.1
0xa652  ldarg.0
0xa653  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa658  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_ClientId()
0xa65d  stelem.ref
0xa65e  dup
0xa65f  ldc.i4.2
0xa660  ldloc.2
0xa661  brtrue.s loc_A66A
0xa663  ldstr    aPingChannel// "Ping Channel"
0xa668  br.s     loc_A66F
0xa66a  ldstr    aExecuteChannel// "Execute Channel"
0xa66f  stelem.ref
0xa670  dup
0xa671  ldc.i4.3
0xa672  ldloc.s  8
0xa674  stelem.ref
0xa675  dup
0xa676  ldc.i4.4
0xa677  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xa67c  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xa681  box      [mscorlib]System.Int32
0xa686  stelem.ref
0xa687  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0xa68c  ldloc.s  0xA
0xa68e  brfalse.s loc_A6EA
0xa690  ldarg.0
0xa691  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa696  ldc.i4.s 0x21
0xa698  ldstr    aSandboxworkerp_32// "SandboxWorkerProcess.CanPingWorkerProce"...
0xa69d  ldc.i4.5
0xa69e  newarr   [mscorlib]System.Object
0xa6a3  dup
0xa6a4  ldc.i4.0
0xa6a5  ldarg.0
0xa6a6  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xa6ab  stelem.ref
0xa6ac  dup
0xa6ad  ldc.i4.1
0xa6ae  ldarg.0
0xa6af  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa6b4  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::get_ClientId()
0xa6b9  stelem.ref
0xa6ba  dup
0xa6bb  ldc.i4.2
0xa6bc  ldloc.2
0xa6bd  brtrue.s loc_A6C6
  ... truncated ...
```
