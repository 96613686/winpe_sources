# Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::Do

- ea: `0xa40`
- end: `0xb07`
- name: `Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::Do`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x9b0`
- `0xa40`
- `0xb70`
- `0xdf0`
- `0xfa0`

## string_xrefs

- `0xa57`: `MSCRMAsyncService`
- `0xa86`: `MSCRMAsyncService$maintenance`
- `0xa8c`: `CrmAsyncService.exe`

## pseudocode

```c

```

## disassembly

```asm
0xa40  ldarg.1
0xa41  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0xa46  stloc.0
0xa47  ldloc.0
0xa48  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_TargetFolder()
0xa4d  ldstr    aServerBin// "Server\\bin"
0xa52  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xa57  ldstr    aMscrmasyncserv// "MSCRMAsyncService"
0xa5c  stloc.1
0xa5d  ldloc.0
0xa5e  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_InstallType()
0xa63  ldc.i4.3
0xa64  bne.un.s loc_A72
0xa66  ldarg.0
0xa67  ldc.i4.1
0xa68  box      [mscorlib]System.Boolean
0xa6d  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::set_Ignorable(object)
0xa72  ldarg.0
0xa73  ldfld    string Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_instance
0xa78  ldarg.0
0xa79  ldfld    string Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_maintenanceInstance
0xa7e  ldc.i4.5
0xa7f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xa84  brfalse.s loc_A8C
0xa86  ldstr    aMscrmasyncserv_0// "MSCRMAsyncService$maintenance"
0xa8b  stloc.1
0xa8c  ldstr    aCrmasyncservic// "CrmAsyncService.exe"
0xa91  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xa96  ldloc.1
0xa97  call     bool Microsoft.Crm.Setup.Common.AsyncServiceInstaller::IsServiceInstalled(string serviceName)
0xa9c  brfalse.s loc_AAF
0xa9e  ldarg.0
0xa9f  ldfld    string Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::_instance
0xaa4  newobj   instance void Microsoft.Crm.Setup.Common.UnregisterAsyncServiceAction::.ctor(string instance)
0xaa9  ldarg.1
0xaaa  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::Do(class [mscorlib]System.Collections.IDictionary)
0xaaf  ldarg.0
0xab0  ldloc.0
0xab1  call     instance string[] Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::CreateInstallParameters(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo installInfo)
0xab6  stloc.2
0xab7  ldloc.2
0xab8  ldloc.1
0xab9  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAssemblyInstaller::.ctor(string, string[], string)
0xabe  stloc.3
0xabf  ldloc.3
0xac0  ldc.i4.1
0xac1  callvirt instance void [System.Configuration.Install]System.Configuration.Install.AssemblyInstaller::set_UseNewContext(bool)
0xac6  ldloc.3
0xac7  ldarg.0
0xac8  ldftn    instance void Microsoft.Crm.Setup.Common.RegisterAsyncServiceAction::OnBeforeInstall(object sender, class [System.Configuration.Install]System.Configuration.Install.InstallEventArgs e)
0xace  newobj   instance void [System.Configuration.Install]System.Configuration.Install.InstallEventHandler::.ctor(object, native int)
0xad3  callvirt instance void [System.Configuration.Install]System.Configuration.Install.Installer::add_BeforeInstall(class [System.Configuration.Install]System.Configuration.Install.InstallEventHandler)
0xad8  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xadd  stloc.s  4
0xadf  ldloc.3
0xae0  ldloc.s  4
0xae2  callvirt instance void [System.Configuration.Install]System.Configuration.Install.Installer::Install(class [mscorlib]System.Collections.IDictionary)
0xae7  ldloc.3
0xae8  ldloc.s  4
0xaea  callvirt instance void [System.Configuration.Install]System.Configuration.Install.Installer::Commit(class [mscorlib]System.Collections.IDictionary)
0xaef  leave.s  loc_AFB
0xaf1  ldloc.3
0xaf2  brfalse.s loc_AFA
0xaf4  ldloc.3
0xaf5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xafa  endfinally
0xafb  newobj   instance void Microsoft.Crm.Setup.Common.RegisterAsyncServicePerformanceCounters::.ctor()
0xb00  ldarg.1
0xb01  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::Do(class [mscorlib]System.Collections.IDictionary)
0xb06  ret
```
