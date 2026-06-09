# Microsoft.Crm.Sandbox.HostService::LogErrorIfSandboxWorkerManagerDidNotStart

- ea: `0x520`
- end: `0x581`
- name: `Microsoft.Crm.Sandbox.HostService::LogErrorIfSandboxWorkerManagerDidNotStart`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x140`

## callees

- `0x520`

## string_xrefs

- `0x542`: `MSCRMSandboxService`
- `0x52b`: `HostService.LogErrorIfSandboxWorkerManagerDidNotStart: PROCESS EXIT: SandboxWorkerManager failed to start - cannot continue`
- `0x575`: `HostService.LogErrorIfSandboxWorkerManagerDidNotStart: PROCESS EXIT: SandboxWorkerManager failed to start - cannot continue`
- `0x55e`: `HostService.InitializeThreadProc: HostService.LogErrorIfSandboxWorkerManagerDidNotStart: PROCESS EXIT: SandboxWorkerManager failed to start - cannot continue`

## pseudocode

```c

```

## disassembly

```asm
0x520  ldarg.0
0x521  brtrue.s loc_580
0x523  ldnull
0x524  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x529  ldc.i4.s 0x26
0x52b  ldstr    aHostserviceLog// "HostService.LogErrorIfSandboxWorkerMana"...
0x530  ldc.i4.0
0x531  newarr   [mscorlib]System.Object
0x536  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x53b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x540  stloc.0
0x541  ldloc.0
0x542  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x547  ldc.i4.1
0x548  ldc.i4   0xC0004F21
0x54d  conv.u8
0x54e  ldc.i4.2
0x54f  newarr   [mscorlib]System.Object
0x554  dup
0x555  ldc.i4.0
0x556  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x55b  stelem.ref
0x55c  dup
0x55d  ldc.i4.1
0x55e  ldstr    aHostserviceIni_4// "HostService.InitializeThreadProc: HostS"...
0x563  stelem.ref
0x564  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x569  leave.s  loc_575
0x56b  ldloc.0
0x56c  brfalse.s loc_574
0x56e  ldloc.0
0x56f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x574  endfinally
0x575  ldstr    aHostserviceLog// "HostService.LogErrorIfSandboxWorkerMana"...
0x57a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x57f  throw
0x580  ret
```
