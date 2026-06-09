# Microsoft.Crm.Sandbox.HostService::OnStop

- ea: `0x70`
- end: `0x136`
- name: `Microsoft.Crm.Sandbox.HostService::OnStop`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x70`
- `0x590`
- `0x32d0`
- `0x4980`
- `0x49a0`
- `0x5590`
- `0x7230`

## string_xrefs

- `0x77`: `HostService.OnStop: enter`
- `0xbf`: `HostService.OnStop: EXCEPTION {0}`
- `0x125`: `HostService.OnStop: EXIT`

## pseudocode

```c

```

## disassembly

```asm
0x70  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x75  ldc.i4.s 0x26
0x77  ldstr    aHostserviceOns_1// "HostService.OnStop: enter"
0x7c  ldc.i4.0
0x7d  newarr   [mscorlib]System.Object
0x82  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x87  call     void Microsoft.Crm.Sandbox.SandboxHost::InitiateShutdown()
0x8c  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::Stop()
0x91  call     void Microsoft.Crm.Sandbox.SandboxAssemblyManager::Stop()
0x96  call     void Microsoft.Crm.Sandbox.SandboxHost::StopListening()
0x9b  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xa0  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xa5  ldc.i4.1
0xa6  bne.un.s loc_AD
0xa8  call     void Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::RemoveAllExistingAccountsInWorkerGroup()
0xad  ldarg.0
0xae  ldc.i4.0
0xaf  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::set_ExitCode(int32)
0xb4  leave.s  loc_F4
0xb6  stloc.0
0xb7  ldloc.0
0xb8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xbd  ldc.i4.s 0x26
0xbf  ldstr    aHostserviceOns_2// "HostService.OnStop: EXCEPTION {0}"
0xc4  ldc.i4.1
0xc5  newarr   [mscorlib]System.Object
0xca  dup
0xcb  ldc.i4.0
0xcc  ldloc.0
0xcd  stelem.ref
0xce  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd3  ldarg.0
0xd4  ldc.i4.1
0xd5  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::set_ExitCode(int32)
0xda  leave.s  loc_F4
0xdc  call     void Microsoft.Crm.Sandbox.HostService::KillRemainingWorkerProcesses()
0xe1  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xe6  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xeb  ldc.i4.1
0xec  bne.un.s loc_F3
0xee  call     void Microsoft.Crm.Sandbox.SandboxWorkerAccountManager::RemoveAllExistingAccountsInWorkerGroup()
0xf3  endfinally
0xf4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0xf9  stloc.1
0xfa  ldloc.1
0xfb  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource()
0x100  ldc.i4.4
0x101  ldc.i4   0x40004F14
0x106  conv.i8
0x107  ldc.i4.0
0x108  newarr   [mscorlib]System.Object
0x10d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x112  leave.s  loc_11E
0x114  ldloc.1
0x115  brfalse.s loc_11D
0x117  ldloc.1
0x118  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11d  endfinally
0x11e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x123  ldc.i4.s 0x26
0x125  ldstr    aHostserviceOns_3// "HostService.OnStop: EXIT"
0x12a  ldc.i4.0
0x12b  newarr   [mscorlib]System.Object
0x130  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x135  ret
```
