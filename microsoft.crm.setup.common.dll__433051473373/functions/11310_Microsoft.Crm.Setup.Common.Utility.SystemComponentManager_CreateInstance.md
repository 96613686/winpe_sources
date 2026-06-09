# Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::CreateInstance

- ea: `0x11310`
- end: `0x11339`
- name: `Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::CreateInstance`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x11310`
- `0x11780`
- `0x11b00`

## string_xrefs

- `0x1131e`: `Detected Windows Server 2012 (or later). Using Powershell SystemComponentManager`

## pseudocode

```c

```

## disassembly

```asm
0x11310  call     bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::get_IsWindowsServer2012OrLater()
0x11315  brfalse.s loc_11330
0x11317  ldarg.0
0x11318  newobj   instance void Microsoft.Crm.Setup.Common.Utility.PowershellSystemComponentManager::.ctor(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo installInfo)
0x1131d  stloc.0
0x1131e  ldstr    aDetectedWindow// "Detected Windows Server 2012 (or later)"...
0x11323  ldc.i4.0
0x11324  newarr   [mscorlib]System.Object
0x11329  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x1132e  br.s     loc_11337
0x11330  ldarg.0
0x11331  newobj   instance void Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::.ctor(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo installInfo)
0x11336  stloc.0
0x11337  ldloc.0
0x11338  ret
```
