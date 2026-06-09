# Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::StartServer

- ea: `0x510`
- end: `0x5a5`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::StartServer`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x510`
- `0xab0`
- `0xb50`

## pseudocode

```c

```

## disassembly

```asm
0x510  newobj   instance void [System]System.Diagnostics.ProcessStartInfo::.ctor()
0x515  dup
0x516  ldc.i4.0
0x517  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_UseShellExecute(bool)
0x51c  dup
0x51d  ldarg.0
0x51e  call     instance bool class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::get_DebugMode()
0x523  brtrue.s loc_528
0x525  ldc.i4.1
0x526  br.s     loc_529
0x528  ldc.i4.0
0x529  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_WindowStyle(valuetype [System]System.Diagnostics.ProcessWindowStyle)
0x52e  dup
0x52f  ldarg.0
0x530  call     instance bool class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::get_DebugMode()
0x535  ldc.i4.0
0x536  ceq
0x538  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_CreateNoWindow(bool)
0x53d  stloc.0
0x53e  ldarg.0
0x53f  ldfld    class [mscorlib]System.Action`1<class [System]System.Diagnostics.ProcessStartInfo> class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::initProcess
0x544  ldloc.0
0x545  callvirt instance void class [mscorlib]System.Action`1<class [System]System.Diagnostics.ProcessStartInfo>::Invoke(var<u1>)
0x54a  newobj   instance void [System]System.Diagnostics.Process::.ctor()
0x54f  dup
0x550  ldloc.0
0x551  callvirt instance void [System]System.Diagnostics.Process::set_StartInfo(class [System]System.Diagnostics.ProcessStartInfo)
0x556  stloc.1
0x557  newobj   instance void Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.Win32ErrorModeHelper::.ctor()
0x55c  stloc.2
0x55d  ldloc.1
0x55e  callvirt instance bool [System]System.Diagnostics.Process::Start()
0x563  pop
0x564  leave.s  loc_570
0x566  ldloc.2
0x567  brfalse.s loc_56F
0x569  ldloc.2
0x56a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x56f  endfinally
0x570  leave.s  loc_590
0x572  stloc.3
0x573  ldstr    aFailedToStartJ// "Failed to start job host process {0} {1"...
0x578  ldloc.0
0x579  callvirt instance string [System]System.Diagnostics.ProcessStartInfo::get_FileName()
0x57e  ldloc.0
0x57f  callvirt instance string [System]System.Diagnostics.ProcessStartInfo::get_Arguments()
0x584  call     string [mscorlib]System.String::Format(string, object, object)
0x589  ldloc.3
0x58a  newobj   instance void Microsoft.Xrm.Tools.OwinJobManager.Client.Exceptions.JobHostException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x58f  throw
0x590  ldarg.0
0x591  call     instance bool class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::get_DebugMode()
0x596  brtrue.s loc_59E
0x598  ldloc.1
0x599  call     void [Microsoft.Xrm.ProcessUtils]Microsoft.Xrm.ProcessUtils.ChildProcessTracker::AddProcess(class [System]System.Diagnostics.Process)
0x59e  ldloc.1
0x59f  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x5a4  ret
```
