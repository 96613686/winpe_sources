# Microsoft.Crm.Sandbox.SandboxWorkerProcess::InitializeWorkerClient

- ea: `0xa0f0`
- end: `0xa34f`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::InitializeWorkerClient`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x7e30`

## callees

- `0x48e0`
- `0x57d0`
- `0x9730`
- `0x9790`
- `0x98f0`
- `0xa0f0`
- `0xa350`
- `0xa7f0`
- `0xb250`

## string_xrefs

- `0xa1b3`: `SandboxWorkerProcess.InitializeWorkerClient:Thread[{0:d4}]: Spent {1} ms in InitializeWorkerClient to successfully initialize a worker`
- `0xa1fa`: `SandboxWorkerProcess.InitializeWorkerClient:Thread[{0:d4}]: Spent {1} ms in Pinging to successfully initialize a worker after {2} attempts`
- `0xa248`: `SandboxWorkerProcess.InitializeWorkerClient:Thread[{0:d4}]: ping failed - sleeping: `
- `0xa29c`: `SandboxWorkerProcess.InitializeWorkerClient:Thread[{0:d4}]: Spent {1} ms in InitializeWorkerClient and did not initialize worker process. Process output:{2}`
- `0xa2fc`: `SandboxWorkerProcess.InitializeWorkerClient:Thread[{0:d4}] HasExited returned Error {1}`

## pseudocode

```c

```

## disassembly

```asm
0xa0f0  ldarg.0
0xa0f1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa0f6  ldc.i4.s 0x21
0xa0f8  ldstr    aSandboxworkerp_19// "SandboxWorkerProcess.InitializeWorkerCl"...
0xa0fd  ldc.i4.0
0xa0fe  newarr   [mscorlib]System.Object
0xa103  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa108  ldarg.0
0xa109  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0xa10e  ldstr    aWorkerprocess// "_workerProcess"
0xa113  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xa118  ldarg.0
0xa119  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa11e  ldstr    aWorkerclient// "_workerClient"
0xa123  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xa128  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xa12d  stloc.0
0xa12e  ldarg.0
0xa12f  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xa134  ldarg.0
0xa135  call     instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0xa13a  ldc.i4.1
0xa13b  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::Start(class [System]System.Uri workerAddress, bool executeClient)
0xa140  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xa145  stloc.1
0xa146  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xa14b  ldc.i4.0
0xa14c  ldc.i4.0
0xa14d  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0xa152  ldc.i4.4
0xa153  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0xa158  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xa15d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xa162  stloc.2
0xa163  ldc.i4.0
0xa164  stloc.3
0xa165  br       loc_A27D
0xa16a  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0xa16f  ldc.i4.5
0xa170  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0xa175  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0xa17a  ldarg.0
0xa17b  call     instance bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::CanPingWorkerProcess()
0xa180  brfalse  loc_A240
0xa185  ldarg.0
0xa186  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa18b  ldc.i4.s 0x21
0xa18d  ldstr    aSandboxworkerp_20// "SandboxWorkerProcess.InitializeWorkerCl"...
0xa192  ldc.i4.1
0xa193  newarr   [mscorlib]System.Object
0xa198  dup
0xa199  ldc.i4.0
0xa19a  ldstr    aPingOk// "ping OK"
0xa19f  stelem.ref
0xa1a0  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa1a5  ldloc.0
0xa1a6  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xa1ab  ldarg.0
0xa1ac  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa1b1  ldc.i4.s 0x21
0xa1b3  ldstr    aSandboxworkerp_21// "SandboxWorkerProcess.InitializeWorkerCl"...
0xa1b8  ldc.i4.2
0xa1b9  newarr   [mscorlib]System.Object
0xa1be  dup
0xa1bf  ldc.i4.0
0xa1c0  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xa1c5  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xa1ca  box      [mscorlib]System.Int32
0xa1cf  stelem.ref
0xa1d0  dup
0xa1d1  ldc.i4.1
0xa1d2  ldloc.0
0xa1d3  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0xa1d8  stloc.s  5
0xa1da  ldloca.s 5
0xa1dc  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0xa1e1  box      [mscorlib]System.Double
0xa1e6  stelem.ref
0xa1e7  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa1ec  ldloc.1
0xa1ed  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xa1f2  ldarg.0
0xa1f3  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa1f8  ldc.i4.s 0x21
0xa1fa  ldstr    aSandboxworkerp_22// "SandboxWorkerProcess.InitializeWorkerCl"...
0xa1ff  ldc.i4.3
0xa200  newarr   [mscorlib]System.Object
0xa205  dup
0xa206  ldc.i4.0
0xa207  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xa20c  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xa211  box      [mscorlib]System.Int32
0xa216  stelem.ref
0xa217  dup
0xa218  ldc.i4.1
0xa219  ldloc.1
0xa21a  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0xa21f  stloc.s  5
0xa221  ldloca.s 5
0xa223  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0xa228  box      [mscorlib]System.Double
0xa22d  stelem.ref
0xa22e  dup
0xa22f  ldc.i4.2
0xa230  ldloc.3
0xa231  ldc.i4.1
0xa232  add
0xa233  box      [mscorlib]System.Int32
0xa238  stelem.ref
0xa239  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa23e  ldc.i4.1
0xa23f  ret
0xa240  ldarg.0
0xa241  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa246  ldc.i4.s 0x21
0xa248  ldstr    aSandboxworkerp_23// "SandboxWorkerProcess.InitializeWorkerCl"...
0xa24d  ldc.i4.2
0xa24e  newarr   [mscorlib]System.Object
0xa253  dup
0xa254  ldc.i4.0
0xa255  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xa25a  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xa25f  box      [mscorlib]System.Int32
0xa264  stelem.ref
0xa265  dup
0xa266  ldc.i4.1
0xa267  ldloca.s 3
0xa269  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa26e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa273  stelem.ref
0xa274  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa279  ldloc.3
0xa27a  ldc.i4.1
0xa27b  add
0xa27c  stloc.3
0xa27d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xa282  ldloc.2
0xa283  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xa288  brtrue   loc_A16A
0xa28d  ldloc.0
0xa28e  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xa293  ldnull
0xa294  ldarg.0
0xa295  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa29a  ldc.i4.s 0x21
0xa29c  ldstr    aSandboxworkerp_24// "SandboxWorkerProcess.InitializeWorkerCl"...
0xa2a1  ldc.i4.3
0xa2a2  newarr   [mscorlib]System.Object
0xa2a7  dup
0xa2a8  ldc.i4.0
0xa2a9  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xa2ae  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xa2b3  box      [mscorlib]System.Int32
0xa2b8  stelem.ref
0xa2b9  dup
0xa2ba  ldc.i4.1
0xa2bb  ldloc.0
0xa2bc  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0xa2c1  stloc.s  5
0xa2c3  ldloca.s 5
0xa2c5  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0xa2ca  box      [mscorlib]System.Double
0xa2cf  stelem.ref
0xa2d0  dup
0xa2d1  ldc.i4.2
0xa2d2  ldarg.0
0xa2d3  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::ReadAllCrashFile()
0xa2d8  stelem.ref
0xa2d9  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa2de  ldc.i4.0
0xa2df  stloc.s  4
0xa2e1  ldarg.0
0xa2e2  call     instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0xa2e7  callvirt instance bool [System]System.Diagnostics.Process::get_HasExited()
0xa2ec  stloc.s  4
0xa2ee  leave.s  loc_A32A
0xa2f0  stloc.s  6
0xa2f2  ldloc.s  6
0xa2f4  ldarg.0
0xa2f5  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa2fa  ldc.i4.s 0x21
0xa2fc  ldstr    aSandboxworkerp_25// "SandboxWorkerProcess.InitializeWorkerCl"...
0xa301  ldc.i4.2
0xa302  newarr   [mscorlib]System.Object
0xa307  dup
0xa308  ldc.i4.0
0xa309  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xa30e  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xa313  box      [mscorlib]System.Int32
0xa318  stelem.ref
0xa319  dup
0xa31a  ldc.i4.1
0xa31b  ldloc.s  6
0xa31d  callvirt instance string [mscorlib]System.Object::ToString()
0xa322  stelem.ref
0xa323  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa328  leave.s  loc_A32A
0xa32a  ldloc.s  4
0xa32c  brtrue.s loc_A34D
0xa32e  ldnull
0xa32f  ldarg.0
0xa330  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xa335  ldc.i4.s 0x21
0xa337  ldstr    aSandboxworkerp_26// "SandboxWorkerProcess.InitializeWorkerCl"...
0xa33c  ldc.i4.0
0xa33d  newarr   [mscorlib]System.Object
0xa342  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa347  ldarg.0
0xa348  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::TerminateProcess()
0xa34d  ldc.i4.0
0xa34e  ret
```
