# Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::StartWindowsService

- ea: `0x2500`
- end: `0x2569`
- name: `Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::StartWindowsService`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2410`

## callees

- `0x20a0`
- `0x2500`

## string_xrefs

- `0x2525`: `{0} service not found on attempt to restart after installing {1}.`
- `0x2545`: `Exception {0} encountered attempting to restart {0} service {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x2500  ldarg.1
0x2501  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor(string)
0x2506  stloc.0
0x2507  ldloc.0
0x2508  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0x250d  ldc.i4.1
0x250e  bne.un.s loc_2516
0x2510  ldloc.0
0x2511  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Start()
0x2516  leave.s  loc_2522
0x2518  ldloc.0
0x2519  brfalse.s loc_2521
0x251b  ldloc.0
0x251c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2521  endfinally
0x2522  leave.s  loc_2568
0x2524  pop
0x2525  ldstr    a0ServiceNotFou// "{0} service not found on attempt to res"...
0x252a  ldc.i4.2
0x252b  newarr   [mscorlib]System.Object
0x2530  dup
0x2531  ldc.i4.0
0x2532  ldarg.1
0x2533  stelem.ref
0x2534  dup
0x2535  ldc.i4.1
0x2536  ldarg.0
0x2537  callvirt instance string Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_ProductName()
0x253c  stelem.ref
0x253d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x2542  leave.s  loc_2568
0x2544  stloc.1
0x2545  ldstr    aException0Enco// "Exception {0} encountered attempting to"...
0x254a  ldc.i4.3
0x254b  newarr   [mscorlib]System.Object
0x2550  dup
0x2551  ldc.i4.0
0x2552  ldloc.1
0x2553  stelem.ref
0x2554  dup
0x2555  ldc.i4.1
0x2556  ldarg.1
0x2557  stelem.ref
0x2558  dup
0x2559  ldc.i4.2
0x255a  ldarg.0
0x255b  callvirt instance string Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_ProductName()
0x2560  stelem.ref
0x2561  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x2566  leave.s  loc_2568
0x2568  ret
```
