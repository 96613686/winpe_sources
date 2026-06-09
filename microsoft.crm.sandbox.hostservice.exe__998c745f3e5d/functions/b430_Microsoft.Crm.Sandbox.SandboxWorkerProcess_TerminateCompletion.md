# Microsoft.Crm.Sandbox.SandboxWorkerProcess::TerminateCompletion

- ea: `0xb430`
- end: `0xb656`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::TerminateCompletion`
- size: `550`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xb250`
- `0xb7b0`

## callees

- `0x8c80`
- `0x9720`
- `0x9730`
- `0xb430`
- `0xb660`

## string_xrefs

- `0xb446`: `SandboxWorkerProcess.TerminateCompletion: enter: {0}`
- `0xb486`: `TerminateCompletion:Thread[{0:d4}] HasExited returned Error {1}`
- `0xb4c1`: `SandboxWorkerProcess.TerminateCompletion: process has already exited`
- `0xb523`: `SandboxWorkerProcess.TerminateCompletion: unexpected: ExitReason: {0}`
- `0xb5fd`: `TerminateCompletion:Thread[{0:d4}] TerminateCompletion returned Error {1}`

## pseudocode

```c

```

## disassembly

```asm
0xb430  ldc.i4.0
0xb431  stloc.0
0xb432  ldarg.0
0xb433  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0xb438  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(valuetype [mscorlib]System.Guid)
0xb43d  stloc.1
0xb43e  ldarg.0
0xb43f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb444  ldc.i4.s 0x26
0xb446  ldstr    aSandboxworkerp_49// "SandboxWorkerProcess.TerminateCompletio"...
0xb44b  ldc.i4.1
0xb44c  newarr   [mscorlib]System.Object
0xb451  dup
0xb452  ldc.i4.0
0xb453  ldarg.0
0xb454  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xb459  stelem.ref
0xb45a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb45f  ldarg.0
0xb460  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0xb465  callvirt instance void [System]System.Diagnostics.Process::Refresh()
0xb46a  ldc.i4.0
0xb46b  stloc.2
0xb46c  ldarg.0
0xb46d  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0xb472  callvirt instance bool [System]System.Diagnostics.Process::get_HasExited()
0xb477  stloc.2
0xb478  leave.s  loc_B4B6
0xb47a  stloc.s  4
0xb47c  ldloc.s  4
0xb47e  ldarg.0
0xb47f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb484  ldc.i4.s 0x21
0xb486  ldstr    aTerminatecompl// "TerminateCompletion:Thread[{0:d4}] HasE"...
0xb48b  ldc.i4.2
0xb48c  newarr   [mscorlib]System.Object
0xb491  dup
0xb492  ldc.i4.0
0xb493  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xb498  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xb49d  box      [mscorlib]System.Int32
0xb4a2  stelem.ref
0xb4a3  dup
0xb4a4  ldc.i4.1
0xb4a5  ldloc.s  4
0xb4a7  callvirt instance string [mscorlib]System.Object::ToString()
0xb4ac  stelem.ref
0xb4ad  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb4b2  ldc.i4.0
0xb4b3  stloc.2
0xb4b4  leave.s  loc_B4B6
0xb4b6  ldloc.2
0xb4b7  brfalse.s loc_B4D8
0xb4b9  ldarg.0
0xb4ba  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb4bf  ldc.i4.s 0x26
0xb4c1  ldstr    aSandboxworkerp_50// "SandboxWorkerProcess.TerminateCompletio"...
0xb4c6  ldc.i4.0
0xb4c7  newarr   [mscorlib]System.Object
0xb4cc  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb4d1  ldc.i4.1
0xb4d2  stloc.0
0xb4d3  leave    loc_B655
0xb4d8  ldarg.0
0xb4d9  ldloca.s 3
0xb4db  ldloca.s 0
0xb4dd  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::KillProcess([out] string& error, [out] bool& terminateSucceeded)
0xb4e2  ldloc.0
0xb4e3  brfalse.s loc_B549
0xb4e5  ldarg.0
0xb4e6  ldfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerProcess::_exitReason
0xb4eb  stloc.s  5
0xb4ed  ldloc.s  5
0xb4ef  ldc.i4.3
0xb4f0  sub
0xb4f1  switch   loc_B510, loc_B51A, loc_B51A, loc_B549, loc_B549, loc_B549
0xb50e  br.s     loc_B51A
0xb510  ldarg.0
0xb511  ldc.i4.s 9
0xb513  stfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerProcess::_exitReason
0xb518  br.s     loc_B549
0xb51a  ldnull
0xb51b  ldarg.0
0xb51c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb521  ldc.i4.s 0x26
0xb523  ldstr    aSandboxworkerp_51// "SandboxWorkerProcess.TerminateCompletio"...
0xb528  ldc.i4.1
0xb529  newarr   [mscorlib]System.Object
0xb52e  dup
0xb52f  ldc.i4.0
0xb530  ldarg.0
0xb531  ldfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerProcess::_exitReason
0xb536  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason
0xb53b  stelem.ref
0xb53c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb541  ldarg.0
0xb542  ldc.i4.s 0xB
0xb544  stfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerProcess::_exitReason
0xb549  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0xb54e  stloc.s  6
0xb550  ldloc.3
0xb551  brfalse.s loc_B597
0xb553  ldloc.s  6
0xb555  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource()
0xb55a  ldc.i4.1
0xb55b  ldc.i4   0xC0004F13
0xb560  conv.u8
0xb561  ldc.i4.4
0xb562  newarr   [mscorlib]System.Object
0xb567  dup
0xb568  ldc.i4.0
0xb569  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0xb56e  stelem.ref
0xb56f  dup
0xb570  ldc.i4.1
0xb571  ldarg.0
0xb572  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xb577  stelem.ref
0xb578  dup
0xb579  ldc.i4.2
0xb57a  ldarg.0
0xb57b  ldflda   valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerProcess::_exitReason
0xb580  constrained. [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason
0xb586  callvirt instance string [mscorlib]System.Object::ToString()
0xb58b  stelem.ref
0xb58c  dup
0xb58d  ldc.i4.3
0xb58e  ldloc.3
0xb58f  stelem.ref
0xb590  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0xb595  br.s     loc_B5D5
0xb597  ldloc.s  6
0xb599  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource()
0xb59e  ldc.i4.2
0xb59f  ldc.i4   0x80004F03
0xb5a4  conv.u8
0xb5a5  ldc.i4.3
0xb5a6  newarr   [mscorlib]System.Object
0xb5ab  dup
0xb5ac  ldc.i4.0
0xb5ad  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0xb5b2  stelem.ref
0xb5b3  dup
0xb5b4  ldc.i4.1
0xb5b5  ldarg.0
0xb5b6  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xb5bb  stelem.ref
0xb5bc  dup
0xb5bd  ldc.i4.2
0xb5be  ldarg.0
0xb5bf  ldflda   valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerProcess::_exitReason
0xb5c4  constrained. [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason
0xb5ca  callvirt instance string [mscorlib]System.Object::ToString()
0xb5cf  stelem.ref
0xb5d0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0xb5d5  leave.s  loc_B5E3
0xb5d7  ldloc.s  6
0xb5d9  brfalse.s loc_B5E2
0xb5db  ldloc.s  6
0xb5dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb5e2  endfinally
0xb5e3  leave.s  loc_B5EF
0xb5e5  ldloc.1
0xb5e6  brfalse.s loc_B5EE
0xb5e8  ldloc.1
0xb5e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb5ee  endfinally
0xb5ef  leave.s  loc_B655
0xb5f1  stloc.s  7
0xb5f3  ldloc.s  7
0xb5f5  ldarg.0
0xb5f6  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb5fb  ldc.i4.s 0x21
0xb5fd  ldstr    aTerminatecompl_0// "TerminateCompletion:Thread[{0:d4}] Term"...
0xb602  ldc.i4.2
0xb603  newarr   [mscorlib]System.Object
0xb608  dup
0xb609  ldc.i4.0
0xb60a  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xb60f  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0xb614  box      [mscorlib]System.Int32
0xb619  stelem.ref
0xb61a  dup
0xb61b  ldc.i4.1
0xb61c  ldloc.s  7
0xb61e  callvirt instance string [mscorlib]System.Object::ToString()
0xb623  stelem.ref
0xb624  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb629  leave.s  loc_B655
0xb62b  ldloc.0
0xb62c  brfalse.s loc_B636
0xb62e  ldarg.0
0xb62f  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::RemoveFromPendingList(class Microsoft.Crm.Sandbox.SandboxWorkerProcess workerProcess)
0xb634  br.s     loc_B654
0xb636  ldarg.0
0xb637  ldarg.0
0xb638  ldftn    instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::TerminateCompletion(object param)
0xb63e  newobj   instance void [mscorlib]System.Threading.TimerCallback::.ctor(object, native int)
0xb643  ldnull
0xb644  ldc.i4   0x1D4C0
0xb649  ldc.i4.m1
0xb64a  newobj   instance void [mscorlib]System.Threading.Timer::.ctor(class [mscorlib]System.Threading.TimerCallback, object, int32, int32)
0xb64f  stfld    class [mscorlib]System.Threading.Timer Microsoft.Crm.Sandbox.SandboxWorkerProcess::_shutdownTimer
0xb654  endfinally
0xb655  ret
```
