# Microsoft.Crm.Sandbox.SandboxWorkerProcess::SnapshotResources

- ea: `0x9930`
- end: `0x9a27`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::SnapshotResources`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xcd60`

## callees

- `0x9730`
- `0x97f0`
- `0x9810`
- `0x9830`
- `0x9930`
- `0xb730`

## string_xrefs

- `0x9988`: `SandboxWorkerProcess.SnapshotResources:Thread[{0:d4}] HasExited returned Error {1}`

## pseudocode

```c

```

## disassembly

```asm
0x9930  ldc.i4.0
0x9931  stloc.0
0x9932  ldarg.0
0x9933  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0x9938  callvirt instance void [System]System.Diagnostics.Process::Refresh()
0x993d  ldarg.0
0x993e  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0x9943  callvirt instance bool [System]System.Diagnostics.Process::get_HasExited()
0x9948  brtrue.s loc_9978
0x994a  ldarg.0
0x994b  ldarg.0
0x994c  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0x9951  callvirt instance int32 [System]System.Diagnostics.Process::get_HandleCount()
0x9956  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::set_HandleCount(int32 value)
0x995b  ldarg.0
0x995c  ldarg.0
0x995d  call     instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::CpuUsage()
0x9962  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::set_Cpu(int32 value)
0x9967  ldarg.0
0x9968  ldarg.0
0x9969  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0x996e  callvirt instance int64 [System]System.Diagnostics.Process::get_PrivateMemorySize64()
0x9973  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::set_Memory(int64 value)
0x9978  ldc.i4.1
0x9979  stloc.0
0x997a  leave    loc_9A25
0x997f  stloc.1
0x9980  ldarg.0
0x9981  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x9986  ldc.i4.s 0x28
0x9988  ldstr    aSandboxworkerp_4// "SandboxWorkerProcess.SnapshotResources:"...
0x998d  ldc.i4.2
0x998e  newarr   [mscorlib]System.Object
0x9993  dup
0x9994  ldc.i4.0
0x9995  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x999a  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x999f  box      [mscorlib]System.Int32
0x99a4  stelem.ref
0x99a5  dup
0x99a6  ldc.i4.1
0x99a7  ldloc.1
0x99a8  callvirt instance string [mscorlib]System.Object::ToString()
0x99ad  stelem.ref
0x99ae  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x99b3  leave.s  loc_9A25
0x99b5  stloc.2
0x99b6  ldarg.0
0x99b7  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x99bc  ldc.i4.s 0x28
0x99be  ldstr    aSandboxworkerp_5// "SandboxWorkerProcess.SnapshotResources:"...
0x99c3  ldc.i4.1
0x99c4  newarr   [mscorlib]System.Object
0x99c9  dup
0x99ca  ldc.i4.0
0x99cb  ldloc.2
0x99cc  callvirt instance string [mscorlib]System.Exception::get_Message()
0x99d1  stelem.ref
0x99d2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x99d7  leave.s  loc_9A25
0x99d9  stloc.3
0x99da  ldarg.0
0x99db  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x99e0  ldc.i4.s 0x28
0x99e2  ldstr    aSandboxworkerp_6// "SandboxWorkerProcess.SnapshotResources:"...
0x99e7  ldc.i4.1
0x99e8  newarr   [mscorlib]System.Object
0x99ed  dup
0x99ee  ldc.i4.0
0x99ef  ldloc.3
0x99f0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x99f5  stelem.ref
0x99f6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x99fb  leave.s  loc_9A25
0x99fd  stloc.s  4
0x99ff  ldloc.s  4
0x9a01  ldarg.0
0x9a02  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x9a07  ldc.i4.s 0x28
0x9a09  ldstr    aSandboxworkerp_7// "SandboxWorkerProcess.SnapshotResources:"...
0x9a0e  ldc.i4.1
0x9a0f  newarr   [mscorlib]System.Object
0x9a14  dup
0x9a15  ldc.i4.0
0x9a16  ldloc.s  4
0x9a18  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9a1d  stelem.ref
0x9a1e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9a23  leave.s  loc_9A25
0x9a25  ldloc.0
0x9a26  ret
```
