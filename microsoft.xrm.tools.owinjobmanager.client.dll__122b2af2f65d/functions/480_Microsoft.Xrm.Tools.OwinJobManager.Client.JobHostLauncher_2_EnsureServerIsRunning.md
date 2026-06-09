# Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::EnsureServerIsRunning

- ea: `0x480`
- end: `0x502`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::EnsureServerIsRunning`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x480`
- `0x9f0`
- `0xb40`

## pseudocode

```c

```

## disassembly

```asm
0x480  ldc.i4.0
0x481  stloc.0
0x482  ldarg.1
0x483  ldc.i4.0
0x484  stind.i1
0x485  ldsfld   object class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::launchLock
0x48a  stloc.1
0x48b  ldc.i4.0
0x48c  stloc.2
0x48d  ldloc.1
0x48e  ldloca.s 2
0x490  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x495  ldc.i4.0
0x496  stloc.3
0x497  br.s     loc_4E3
0x499  nop
0x49a  ldarg.0
0x49b  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0> class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::client
0x4a0  callvirt instance int32 class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::GetHostProcessId()
0x4a5  stloc.s  4
0x4a7  ldarg.1
0x4a8  ldloc.s  4
0x4aa  ldloc.0
0x4ab  ceq
0x4ad  stind.i1
0x4ae  ldloc.3
0x4af  ldc.i4.1
0x4b0  add
0x4b1  stloc.s  5
0x4b3  leave.s  loc_4FF
0x4b5  isinst   [System.Net.Http]System.Net.Http.HttpRequestException
0x4ba  dup
0x4bb  brtrue.s loc_4C1
0x4bd  pop
0x4be  ldc.i4.0
0x4bf  br.s     loc_4C9
0x4c1  call     bool Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::IsConnectFailure(class [System.Net.Http]System.Net.Http.HttpRequestException ex)
0x4c6  ldc.i4.0
0x4c7  cgt.un
0x4c9  endfilter
0x4cb  pop
0x4cc  ldarg.0
0x4cd  call     instance int32 class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::StartServer()
0x4d2  stloc.0
0x4d3  ldc.i4   0xBB8
0x4d8  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x4dd  leave.s  loc_4DF
0x4df  ldloc.3
0x4e0  ldc.i4.1
0x4e1  add
0x4e2  stloc.3
0x4e3  ldloc.3
0x4e4  ldc.i4.s 0xA
0x4e6  blt.s    loc_499
0x4e8  leave.s  loc_4F4
0x4ea  ldloc.2
0x4eb  brfalse.s loc_4F3
0x4ed  ldloc.1
0x4ee  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x4f3  endfinally
0x4f4  ldstr    aFailedToConnec// "Failed to connect or start API Host"
0x4f9  newobj   instance void Microsoft.Xrm.Tools.OwinJobManager.Client.Exceptions.JobHostException::.ctor(string message)
0x4fe  throw
0x4ff  ldloc.s  5
0x501  ret
```
