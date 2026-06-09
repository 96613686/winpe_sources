# Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit

- ea: `0x9de0`
- end: `0x9ed1`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit`
- size: `241`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x22b0`
- `0x4130`
- `0x7150`
- `0x78c0`
- `0xcd60`

## callees

- `0x5770`
- `0x8620`
- `0x9720`
- `0x9730`
- `0x9de0`
- `0xb250`
- `0xb660`

## string_xrefs

- `0x9e30`: `SandboxWorkerProcess.Exit: Exit called on a process that is already exiting. Process status: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x9de0  ldarg.0
0x9de1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0x9de6  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(valuetype [mscorlib]System.Guid)
0x9deb  stloc.0
0x9dec  ldarg.0
0x9ded  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x9df2  ldc.i4.s 0x26
0x9df4  ldstr    aSandboxworkerp_12// "SandboxWorkerProcess.Exit: enter for pr"...
0x9df9  ldc.i4.2
0x9dfa  newarr   [mscorlib]System.Object
0x9dff  dup
0x9e00  ldc.i4.0
0x9e01  ldarg.0
0x9e02  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0x9e07  stelem.ref
0x9e08  dup
0x9e09  ldc.i4.1
0x9e0a  ldarg.1
0x9e0b  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason
0x9e10  stelem.ref
0x9e11  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9e16  ldarg.0
0x9e17  ldfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerProcess::_exitReason
0x9e1c  brtrue.s loc_9E27
0x9e1e  ldarg.0
0x9e1f  ldarg.1
0x9e20  stfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerProcess::_exitReason
0x9e25  br.s     loc_9E4E
0x9e27  ldnull
0x9e28  ldarg.0
0x9e29  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x9e2e  ldc.i4.s 0x26
0x9e30  ldstr    aSandboxworkerp_13// "SandboxWorkerProcess.Exit: Exit called "...
0x9e35  ldc.i4.1
0x9e36  newarr   [mscorlib]System.Object
0x9e3b  dup
0x9e3c  ldc.i4.0
0x9e3d  ldarg.0
0x9e3e  ldfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerProcess::_exitReason
0x9e43  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason
0x9e48  stelem.ref
0x9e49  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9e4e  ldarg.1
0x9e4f  ldc.i4.4
0x9e50  bne.un.s loc_9E60
0x9e52  ldarg.0
0x9e53  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0x9e58  ldc.i4.5
0x9e59  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus value)
0x9e5e  br.s     loc_9E6C
0x9e60  ldarg.0
0x9e61  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0x9e66  ldc.i4.4
0x9e67  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus value)
0x9e6c  nop
0x9e6d  ldarg.0
0x9e6e  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::TerminateProcess()
0x9e73  leave.s  loc_9ED0
0x9e75  stloc.1
0x9e76  ldloc.1
0x9e77  ldarg.0
0x9e78  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x9e7d  ldc.i4.s 0x26
0x9e7f  ldstr    aSandboxworkerp_14// "SandboxWorkerProcess.Exit: Exception ca"...
0x9e84  ldc.i4.1
0x9e85  newarr   [mscorlib]System.Object
0x9e8a  dup
0x9e8b  ldc.i4.0
0x9e8c  ldloc.1
0x9e8d  stelem.ref
0x9e8e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9e93  ldarg.0
0x9e94  ldloca.s 2
0x9e96  ldloca.s 3
0x9e98  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::KillProcess([out] string& error, [out] bool& terminateSucceeded)
0x9e9d  ldloc.3
0x9e9e  brtrue.s loc_9EBD
0x9ea0  ldloc.1
0x9ea1  ldarg.0
0x9ea2  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x9ea7  ldc.i4.s 0x26
0x9ea9  ldstr    aSandboxworkerp_15// "SandboxWorkerProcess.Exit: Error killin"...
0x9eae  ldc.i4.1
0x9eaf  newarr   [mscorlib]System.Object
0x9eb4  dup
0x9eb5  ldc.i4.0
0x9eb6  ldloc.2
0x9eb7  stelem.ref
0x9eb8  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9ebd  leave.s  loc_9ED0
0x9ebf  ldloc.0
0x9ec0  brfalse.s loc_9EC8
0x9ec2  ldloc.0
0x9ec3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9ec8  endfinally
0x9ec9  ldarg.0
0x9eca  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::ProcessDeletedWorker(class Microsoft.Crm.Sandbox.SandboxWorkerProcess workerProcess)
0x9ecf  endfinally
0x9ed0  ret
```
