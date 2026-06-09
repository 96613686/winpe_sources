# Microsoft.Crm.Setup.Common.UnregisterAsyncServiceAction::Do

- ea: `0xe20`
- end: `0xf8f`
- name: `Microsoft.Crm.Setup.Common.UnregisterAsyncServiceAction::Do`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x9b0`
- `0xe20`

## string_xrefs

- `0xe20`: `MSCRMAsyncService`
- `0xe40`: `MSCRMAsyncService$maintenance`
- `0xea0`: `CrmAsyncService.exe`
- `0xf17`: `CrmAsyncService.log`
- `0xf64`: `CrmAsyncService.log`

## pseudocode

```c

```

## disassembly

```asm
0xe20  ldstr    aMscrmasyncserv// "MSCRMAsyncService"
0xe25  stloc.0
0xe26  ldstr    aServerBin// "Server\\bin"
0xe2b  stloc.1
0xe2c  ldarg.0
0xe2d  ldfld    string Microsoft.Crm.Setup.Common.UnregisterAsyncServiceAction::_instance
0xe32  ldarg.0
0xe33  ldfld    string Microsoft.Crm.Setup.Common.UnregisterAsyncServiceAction::_maintenanceInstance
0xe38  ldc.i4.5
0xe39  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xe3e  brfalse.s loc_E46
0xe40  ldstr    aMscrmasyncserv_0// "MSCRMAsyncService$maintenance"
0xe45  stloc.0
0xe46  ldloc.0
0xe47  call     bool Microsoft.Crm.Setup.Common.AsyncServiceInstaller::IsServiceInstalled(string serviceName)
0xe4c  brfalse  loc_F8E
0xe51  ldloc.0
0xe52  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::.ctor(string)
0xe57  stloc.2
0xe58  ldloc.2
0xe59  stloc.3
0xe5a  ldloc.2
0xe5b  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0xe60  ldc.i4.1
0xe61  beq.s    loc_E72
0xe63  ldloc.2
0xe64  callvirt instance valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus [System.ServiceProcess]System.ServiceProcess.ServiceController::get_Status()
0xe69  ldc.i4.3
0xe6a  beq.s    loc_E72
0xe6c  ldloc.2
0xe6d  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::Stop()
0xe72  ldloc.2
0xe73  ldc.i4.1
0xe74  ldc.r8   1.0
0xe7d  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0xe82  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0xe87  ldarg.1
0xe88  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0xe8d  stloc.s  4
0xe8f  ldloc.s  4
0xe91  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_TargetFolder()
0xe96  ldloc.1
0xe97  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xe9c  stloc.s  5
0xe9e  ldloc.s  5
0xea0  ldstr    aCrmasyncservic// "CrmAsyncService.exe"
0xea5  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xeaa  stloc.s  5
0xeac  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IsolatedAssemblyUninstaller::.ctor()
0xeb1  stloc.s  6
0xeb3  ldarg.0
0xeb4  ldfld    string Microsoft.Crm.Setup.Common.UnregisterAsyncServiceAction::_instance
0xeb9  ldarg.0
0xeba  ldfld    string Microsoft.Crm.Setup.Common.UnregisterAsyncServiceAction::_maintenanceInstance
0xebf  ldc.i4.5
0xec0  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xec5  brfalse.s loc_F3E
0xec7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xecc  stloc.s  7
0xece  ldstr    aInstance0// "/instance={0}"
0xed3  stloc.s  8
0xed5  ldloc.s  7
0xed7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xedc  ldloc.s  8
0xede  ldc.i4.1
0xedf  newarr   [mscorlib]System.Object
0xee4  dup
0xee5  ldc.i4.0
0xee6  ldarg.0
0xee7  ldfld    string Microsoft.Crm.Setup.Common.UnregisterAsyncServiceAction::_instance
0xeec  stelem.ref
0xeed  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xef2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xef7  ldloc.s  7
0xef9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xefe  ldstr    aLogfile0// "/logfile={0}"
0xf03  ldc.i4.1
0xf04  newarr   [mscorlib]System.Object
0xf09  dup
0xf0a  ldc.i4.0
0xf0b  ldloc.s  4
0xf0d  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_LogFile()
0xf12  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0xf17  ldstr    aCrmasyncservic_0// "CrmAsyncService.log"
0xf1c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xf21  stelem.ref
0xf22  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf27  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xf2c  ldloc.s  6
0xf2e  ldloc.s  5
0xf30  ldloc.s  7
0xf32  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0xf37  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IsolatedAssemblyUninstaller::DoInOwnAppDomain(string, string[])
0xf3c  leave.s  loc_F8E
0xf3e  ldc.i4.1
0xf3f  newarr   [mscorlib]System.String
0xf44  dup
0xf45  ldc.i4.0
0xf46  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf4b  ldstr    aLogfile0// "/logfile={0}"
0xf50  ldc.i4.1
0xf51  newarr   [mscorlib]System.Object
0xf56  dup
0xf57  ldc.i4.0
0xf58  ldloc.s  4
0xf5a  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_LogFile()
0xf5f  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0xf64  ldstr    aCrmasyncservic_0// "CrmAsyncService.log"
0xf69  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xf6e  stelem.ref
0xf6f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf74  stelem.ref
0xf75  stloc.s  9
0xf77  ldloc.s  6
0xf79  ldloc.s  5
0xf7b  ldloc.s  9
0xf7d  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IsolatedAssemblyUninstaller::DoInOwnAppDomain(string, string[])
0xf82  leave.s  loc_F8E
0xf84  ldloc.3
0xf85  brfalse.s loc_F8D
0xf87  ldloc.3
0xf88  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf8d  endfinally
0xf8e  ret
```
