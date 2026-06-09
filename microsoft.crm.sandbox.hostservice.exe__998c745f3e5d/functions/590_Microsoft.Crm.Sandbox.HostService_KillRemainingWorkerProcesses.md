# Microsoft.Crm.Sandbox.HostService::KillRemainingWorkerProcesses

- ea: `0x590`
- end: `0x6eb`
- name: `Microsoft.Crm.Sandbox.HostService::KillRemainingWorkerProcesses`
- size: `347`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x70`
- `0x140`

## callees

- `0x590`

## string_xrefs

- `0x5b1`: `HostService.KillRemainingWorkerProcesses: Warning: Found {0} remaining drawbridge worker processes. SandboxWorkerManager should've killed them on Stop(). Task killing them again.`
- `0x5e9`: `HostService.KillRemainingWorkerProcesses: Exception thrown when killing drawbridge workerProcess: {0}`
- `0x615`: `HostService.KillRemainingWorkerProcesses: Warning: Found {0} remaining native worker processes. SandboxWorkerManager should've killed them on Stop(). Task killing them again.`
- `0x64d`: `HostService.KillRemainingWorkerProcesses: Exception thrown when killing native workerProcess: {0}`
- `0x68b`: `HostService.KillRemainingWorkerProcesses: Exception thrown when waiting for workerProcess to exit: {0}`
- `0x6c9`: `HostService.KillRemainingWorkerProcesses: Exception thrown when waiting for workerProcess to exit: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x590  ldstr    aDkmon// "DkMon"
0x595  call     class [System]System.Diagnostics.Process[] [System]System.Diagnostics.Process::GetProcessesByName(string)
0x59a  stloc.0
0x59b  ldstr    aMicrosoftCrmSa// "Microsoft.Crm.Sandbox.WorkerProcess"
0x5a0  call     class [System]System.Diagnostics.Process[] [System]System.Diagnostics.Process::GetProcessesByName(string)
0x5a5  stloc.1
0x5a6  ldloc.0
0x5a7  ldlen
0x5a8  brfalse.s loc_60A
0x5aa  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5af  ldc.i4.s 0x26
0x5b1  ldstr    aHostserviceKil// "HostService.KillRemainingWorkerProcesse"...
0x5b6  ldc.i4.1
0x5b7  newarr   [mscorlib]System.Object
0x5bc  dup
0x5bd  ldc.i4.0
0x5be  ldloc.0
0x5bf  ldlen
0x5c0  conv.i4
0x5c1  box      [mscorlib]System.Int32
0x5c6  stelem.ref
0x5c7  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5cc  ldloc.0
0x5cd  stloc.2
0x5ce  ldc.i4.0
0x5cf  stloc.3
0x5d0  br.s     loc_604
0x5d2  ldloc.2
0x5d3  ldloc.3
0x5d4  ldelem.ref
0x5d5  stloc.s  4
0x5d7  ldloc.s  4
0x5d9  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x5de  leave.s  loc_600
0x5e0  stloc.s  5
0x5e2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5e7  ldc.i4.s 0x26
0x5e9  ldstr    aHostserviceKil_0// "HostService.KillRemainingWorkerProcesse"...
0x5ee  ldc.i4.1
0x5ef  newarr   [mscorlib]System.Object
0x5f4  dup
0x5f5  ldc.i4.0
0x5f6  ldloc.s  5
0x5f8  stelem.ref
0x5f9  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5fe  leave.s  loc_600
0x600  ldloc.3
0x601  ldc.i4.1
0x602  add
0x603  stloc.3
0x604  ldloc.3
0x605  ldloc.2
0x606  ldlen
0x607  conv.i4
0x608  blt.s    loc_5D2
0x60a  ldloc.1
0x60b  ldlen
0x60c  brfalse.s loc_66E
0x60e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x613  ldc.i4.s 0x26
0x615  ldstr    aHostserviceKil_1// "HostService.KillRemainingWorkerProcesse"...
0x61a  ldc.i4.1
0x61b  newarr   [mscorlib]System.Object
0x620  dup
0x621  ldc.i4.0
0x622  ldloc.1
0x623  ldlen
0x624  conv.i4
0x625  box      [mscorlib]System.Int32
0x62a  stelem.ref
0x62b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x630  ldloc.1
0x631  stloc.2
0x632  ldc.i4.0
0x633  stloc.3
0x634  br.s     loc_668
0x636  ldloc.2
0x637  ldloc.3
0x638  ldelem.ref
0x639  stloc.s  6
0x63b  ldloc.s  6
0x63d  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x642  leave.s  loc_664
0x644  stloc.s  7
0x646  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x64b  ldc.i4.s 0x26
0x64d  ldstr    aHostserviceKil_2// "HostService.KillRemainingWorkerProcesse"...
0x652  ldc.i4.1
0x653  newarr   [mscorlib]System.Object
0x658  dup
0x659  ldc.i4.0
0x65a  ldloc.s  7
0x65c  stelem.ref
0x65d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x662  leave.s  loc_664
0x664  ldloc.3
0x665  ldc.i4.1
0x666  add
0x667  stloc.3
0x668  ldloc.3
0x669  ldloc.2
0x66a  ldlen
0x66b  conv.i4
0x66c  blt.s    loc_636
0x66e  ldloc.0
0x66f  stloc.2
0x670  ldc.i4.0
0x671  stloc.3
0x672  br.s     loc_6A6
0x674  ldloc.2
0x675  ldloc.3
0x676  ldelem.ref
0x677  stloc.s  8
0x679  ldloc.s  8
0x67b  callvirt instance void [System]System.Diagnostics.Process::WaitForExit()
0x680  leave.s  loc_6A2
0x682  stloc.s  9
0x684  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x689  ldc.i4.s 0x26
0x68b  ldstr    aHostserviceKil_3// "HostService.KillRemainingWorkerProcesse"...
0x690  ldc.i4.1
0x691  newarr   [mscorlib]System.Object
0x696  dup
0x697  ldc.i4.0
0x698  ldloc.s  9
0x69a  stelem.ref
0x69b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6a0  leave.s  loc_6A2
0x6a2  ldloc.3
0x6a3  ldc.i4.1
0x6a4  add
0x6a5  stloc.3
0x6a6  ldloc.3
0x6a7  ldloc.2
0x6a8  ldlen
0x6a9  conv.i4
0x6aa  blt.s    loc_674
0x6ac  ldloc.1
0x6ad  stloc.2
0x6ae  ldc.i4.0
0x6af  stloc.3
0x6b0  br.s     loc_6E4
0x6b2  ldloc.2
0x6b3  ldloc.3
0x6b4  ldelem.ref
0x6b5  stloc.s  0xA
0x6b7  ldloc.s  0xA
0x6b9  callvirt instance void [System]System.Diagnostics.Process::WaitForExit()
0x6be  leave.s  loc_6E0
0x6c0  stloc.s  0xB
0x6c2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6c7  ldc.i4.s 0x26
0x6c9  ldstr    aHostserviceKil_3// "HostService.KillRemainingWorkerProcesse"...
0x6ce  ldc.i4.1
0x6cf  newarr   [mscorlib]System.Object
0x6d4  dup
0x6d5  ldc.i4.0
0x6d6  ldloc.s  0xB
0x6d8  stelem.ref
0x6d9  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6de  leave.s  loc_6E0
0x6e0  ldloc.3
0x6e1  ldc.i4.1
0x6e2  add
0x6e3  stloc.3
0x6e4  ldloc.3
0x6e5  ldloc.2
0x6e6  ldlen
0x6e7  conv.i4
0x6e8  blt.s    loc_6B2
0x6ea  ret
```
