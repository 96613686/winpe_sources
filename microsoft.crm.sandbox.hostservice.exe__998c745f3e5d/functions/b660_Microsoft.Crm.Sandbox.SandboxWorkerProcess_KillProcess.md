# Microsoft.Crm.Sandbox.SandboxWorkerProcess::KillProcess

- ea: `0xb660`
- end: `0xb723`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::KillProcess`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x9de0`
- `0xb430`

## callees

- `0x9730`
- `0xb660`

## string_xrefs

- `0xb673`: `SandboxWorkerProcess.TerminateCompletion: terminate worker process: {0}`
- `0xb6c3`: `SandboxWorkerProcess.TerminateCompletion: Process did not had time to clean up: {0}`
- `0xb707`: `SandboxWorkerProcess.TerminateCompletion: terminate failed: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xb660  ldarg.1
0xb661  ldsfld   string [mscorlib]System.String::Empty
0xb666  stind.ref
0xb667  ldarg.2
0xb668  ldc.i4.0
0xb669  stind.i1
0xb66a  ldnull
0xb66b  ldarg.0
0xb66c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb671  ldc.i4.s 0x26
0xb673  ldstr    aSandboxworkerp_52// "SandboxWorkerProcess.TerminateCompletio"...
0xb678  ldc.i4.1
0xb679  newarr   [mscorlib]System.Object
0xb67e  dup
0xb67f  ldc.i4.0
0xb680  ldarg.0
0xb681  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xb686  stelem.ref
0xb687  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb68c  ldarg.0
0xb68d  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0xb692  callvirt instance void [System]System.Diagnostics.Process::Kill()
0xb697  ldarg.0
0xb698  ldfld    class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerProcess
0xb69d  ldc.r8   1.0
0xb6a6  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0xb6ab  stloc.0
0xb6ac  ldloca.s 0
0xb6ae  call     instance int32 [mscorlib]System.TimeSpan::get_Milliseconds()
0xb6b3  callvirt instance bool [System]System.Diagnostics.Process::WaitForExit(int32)
0xb6b8  brtrue.s loc_B6E1
0xb6ba  ldnull
0xb6bb  ldarg.0
0xb6bc  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb6c1  ldc.i4.s 0x26
0xb6c3  ldstr    aSandboxworkerp_53// "SandboxWorkerProcess.TerminateCompletio"...
0xb6c8  ldc.i4.1
0xb6c9  newarr   [mscorlib]System.Object
0xb6ce  dup
0xb6cf  ldc.i4.0
0xb6d0  ldarg.0
0xb6d1  ldfld    string Microsoft.Crm.Sandbox.SandboxWorkerProcess::_fullId
0xb6d6  stelem.ref
0xb6d7  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb6dc  ldarg.2
0xb6dd  ldc.i4.0
0xb6de  stind.i1
0xb6df  br.s     loc_B6E4
0xb6e1  ldarg.2
0xb6e2  ldc.i4.1
0xb6e3  stind.i1
0xb6e4  leave.s  loc_B722
0xb6e6  stloc.1
0xb6e7  ldarg.1
0xb6e8  ldloc.1
0xb6e9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xb6ee  ldstr    asc_12434// ": "
0xb6f3  ldloc.1
0xb6f4  callvirt instance string [mscorlib]System.Exception::get_Message()
0xb6f9  call     string [mscorlib]System.String::Concat(object, object, object)
0xb6fe  stind.ref
0xb6ff  ldarg.0
0xb700  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0xb705  ldc.i4.s 0x26
0xb707  ldstr    aSandboxworkerp_54// "SandboxWorkerProcess.TerminateCompletio"...
0xb70c  ldc.i4.1
0xb70d  newarr   [mscorlib]System.Object
0xb712  dup
0xb713  ldc.i4.0
0xb714  ldloc.1
0xb715  callvirt instance string [mscorlib]System.Exception::get_Message()
0xb71a  stelem.ref
0xb71b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb720  leave.s  loc_B722
0xb722  ret
```
