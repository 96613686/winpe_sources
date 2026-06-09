# Microsoft.Crm.Sandbox.SandboxWorkerProcess::TerminateProcess

- ea: `0xb250`
- end: `0xb428`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::TerminateProcess`
- size: `472`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x7230`
- `0x7e30`
- `0x94e0`
- `0x9de0`
- `0xa0f0`

## callees

- `0x4900`
- `0x5770`
- `0x8620`
- `0x8c60`
- `0x9730`
- `0x97a0`
- `0xb250`
- `0xb430`

## string_xrefs

- `0xb281`: `SandboxWorkerProcess.TerminateProcess: process is already terminated`
- `0xb336`: `SandboxWorkerProcess.TerminateProcess:Thread[{0:d4}] HasExited returned Error {1}`
- `0xb370`: `SandboxWorkerProcess.TerminateProcess: process has already exited`

## pseudocode

```c

```

## disassembly

```asm
0xb250  ldarg.0
0xb251  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb256  ldc.i4.s 0x26
0xb258  ldstr    aSandboxworkerp_43// "SandboxWorkerProcess.TerminateProcess: "...
0xb25d  ldc.i4.1
0xb25e  newarr   [mscorlib]System.Object
0xb263  dup
0xb264  ldc.i4.0
0xb265  ldarg.0
0xb266  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xb26b  stelem.ref
0xb26c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb271  ldarg.0
0xb272  ldfld    bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::_processTerminated
0xb277  brfalse.s loc_B296
0xb279  ldarg.0
0xb27a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb27f  ldc.i4.s 0x26
0xb281  ldstr    aSandboxworkerp_44// "SandboxWorkerProcess.TerminateProcess: "...
0xb286  ldc.i4.0
0xb287  newarr   [mscorlib]System.Object
0xb28c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb291  leave    loc_B427
0xb296  ldarg.0
0xb297  ldc.i4.1
0xb298  stfld    bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::_processTerminated
0xb29d  ldarg.0
0xb29e  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32> Microsoft.Crm.Sandbox.SandboxWorkerProcess::_portsQueue
0xb2a3  ldarg.0
0xb2a4  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::WorkerPort
0xb2a9  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32>::Enqueue(var<u1>)
0xb2ae  ldarg.0
0xb2af  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0xb2b4  brtrue.s loc_B2D3
0xb2b6  ldarg.0
0xb2b7  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb2bc  ldc.i4.s 0x26
0xb2be  ldstr    aSandboxworkerp_45// "SandboxWorkerProcess.TerminateProcess: "...
0xb2c3  ldc.i4.0
0xb2c4  newarr   [mscorlib]System.Object
0xb2c9  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb2ce  leave    loc_B427
0xb2d3  ldarg.0
0xb2d4  ldfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerProcess::_exitReason
0xb2d9  ldc.i4.4
0xb2da  bne.un.s loc_B2EA
0xb2dc  ldarg.0
0xb2dd  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xb2e2  ldc.i4.5
0xb2e3  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus value)
0xb2e8  br.s     loc_B2F6
0xb2ea  ldarg.0
0xb2eb  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0xb2f0  ldc.i4.4
0xb2f1  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus value)
0xb2f6  ldarg.0
0xb2f7  call     instance bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_AssignedToOrganization()
0xb2fc  brfalse.s loc_B311
0xb2fe  ldarg.0
0xb2ff  ldftn    instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::ExitProcessing(object notUsed)
0xb305  newobj   instance void [mscorlib]System.Threading.WaitCallback::.ctor(object, native int)
0xb30a  ldnull
0xb30b  call     bool [mscorlib]System.Threading.ThreadPool::QueueUserWorkItem(class [mscorlib]System.Threading.WaitCallback, object)
0xb310  pop
0xb311  ldarg.0
0xb312  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0xb317  callvirt instance void [System]System.Diagnostics.Process::Refresh()
0xb31c  ldc.i4.0
0xb31d  stloc.0
0xb31e  ldarg.0
0xb31f  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0xb324  callvirt instance bool [System]System.Diagnostics.Process::get_HasExited()
0xb329  stloc.0
0xb32a  leave.s  loc_B365
0xb32c  stloc.3
0xb32d  ldloc.3
0xb32e  ldarg.0
0xb32f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb334  ldc.i4.s 0x21
0xb336  ldstr    aSandboxworkerp_46// "SandboxWorkerProcess.TerminateProcess:T"...
0xb33b  ldc.i4.2
0xb33c  newarr   [mscorlib]System.Object
0xb341  dup
0xb342  ldc.i4.0
0xb343  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xb348  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xb34d  box      [mscorlib]System.Int32
0xb352  stelem.ref
0xb353  dup
0xb354  ldc.i4.1
0xb355  ldloc.3
0xb356  callvirt instance string [mscorlib]System.Object::ToString()
0xb35b  stelem.ref
0xb35c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb361  ldc.i4.0
0xb362  stloc.0
0xb363  leave.s  loc_B365
0xb365  ldloc.0
0xb366  brfalse.s loc_B385
0xb368  ldarg.0
0xb369  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb36e  ldc.i4.s 0x26
0xb370  ldstr    aSandboxworkerp_47// "SandboxWorkerProcess.TerminateProcess: "...
0xb375  ldc.i4.0
0xb376  newarr   [mscorlib]System.Object
0xb37b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb380  leave    loc_B427
0xb385  ldarg.0
0xb386  ldfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerProcess::_exitReason
0xb38b  stloc.s  4
0xb38d  ldloc.s  4
0xb38f  ldc.i4.6
0xb390  sub
0xb391  switch   loc_B3A4, loc_B3A4, loc_B3A4
0xb3a2  br.s     loc_B3AD
0xb3a4  ldarg.0
0xb3a5  ldnull
0xb3a6  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::TerminateCompletion(object param)
0xb3ab  leave.s  loc_B427
0xb3ad  ldc.i4.3
0xb3ae  ldarg.0
0xb3af  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_operationTimeoutInSec
0xb3b4  mul
0xb3b5  stloc.1
0xb3b6  ldarg.0
0xb3b7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb3bc  stloc.s  5
0xb3be  ldloca.s 5
0xb3c0  ldloc.1
0xb3c1  conv.r8
0xb3c2  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0xb3c7  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.SandboxWorkerProcess::_terminateTime
0xb3cc  ldc.i4.s 0x3C
0xb3ce  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostWorkerConfiguration()
0xb3d3  ldc.i4.5
0xb3d4  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty)
0xb3d9  mul
0xb3da  stloc.2
0xb3db  ldloc.1
0xb3dc  ldloc.2
0xb3dd  bgt.s    loc_B3F8
0xb3df  ldnull
0xb3e0  ldarg.0
0xb3e1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb3e6  ldc.i4.s 0x26
0xb3e8  ldstr    aSandboxworkerp_48// "SandboxWorkerProcess.TerminateProcess: "...
0xb3ed  ldc.i4.0
0xb3ee  newarr   [mscorlib]System.Object
0xb3f3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb3f8  ldarg.0
0xb3f9  ldarg.0
0xb3fa  ldftn    instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::TerminateCompletion(object param)
0xb400  newobj   instance void [mscorlib]System.Threading.TimerCallback::.ctor(object, native int)
0xb405  ldnull
0xb406  ldloc.1
0xb407  ldc.i4   0x3E8
0xb40c  mul
0xb40d  ldc.i4.m1
0xb40e  newobj   instance void [mscorlib]System.Threading.Timer::.ctor(class [mscorlib]System.Threading.TimerCallback, object, int32, int32)
0xb413  stfld    class [mscorlib]System.Threading.Timer Microsoft.Crm.Sandbox.SandboxWorkerProcess::_shutdownTimer
0xb418  ldarg.0
0xb419  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::AddToPendingList(class Microsoft.Crm.Sandbox.SandboxWorkerProcess workerProcess)
0xb41e  leave.s  loc_B427
0xb420  ldarg.0
0xb421  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::ProcessDeletedWorker(class Microsoft.Crm.Sandbox.SandboxWorkerProcess workerProcess)
0xb426  endfinally
0xb427  ret
```
