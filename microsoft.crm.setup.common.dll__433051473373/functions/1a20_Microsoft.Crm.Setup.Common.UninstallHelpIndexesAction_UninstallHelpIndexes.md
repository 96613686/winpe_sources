# Microsoft.Crm.Setup.Common.UninstallHelpIndexesAction::UninstallHelpIndexes

- ea: `0x1a20`
- end: `0x1ac8`
- name: `Microsoft.Crm.Setup.Common.UninstallHelpIndexesAction::UninstallHelpIndexes`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x19f0`

## callees

- `0xff0`
- `0x14e0`
- `0x1a20`

## string_xrefs

- `0x1a75`: `UninstallHelpIndexesAction.ProgressMessage`

## pseudocode

```c

```

## disassembly

```asm
0x1a20  ldarg.0
0x1a21  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.UninstallHelpIndexesAction::installer
0x1a26  ldarg.1
0x1a27  ldarg.0
0x1a28  call     instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ActionWithProgress::get_ProgressStart()
0x1a2d  ldarg.0
0x1a2e  call     instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ActionWithProgress::get_AllocatedProgress()
0x1a33  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ExternalInstallEventHandler::.ctor(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource, class [mscorlib]System.Collections.IDictionary, int32, int32)
0x1a38  stloc.0
0x1a39  ldc.i4.0
0x1a3a  stloc.1
0x1a3b  newobj   instance void [ISWrapper]Microsoft.Crm.Tools.ISWrapper.AdminIndexServerClass::.ctor()
0x1a40  stloc.2
0x1a41  ldloc.2
0x1a42  ldarg.0
0x1a43  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.UninstallHelpIndexesAction::installer
0x1a48  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_CatalogName()
0x1a4d  callvirt instance object [ISWrapper]Microsoft.Crm.Tools.ISWrapper.IAdminIndexServer::GetCatalogByName(string)
0x1a52  pop
0x1a53  leave.s  loc_1A6F
0x1a55  stloc.3
0x1a56  ldc.i4   0x490
0x1a5b  ldloc.3
0x1a5c  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x1a61  call     int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::Win32ErrorFromHResult(int32)
0x1a66  bne.un.s loc_1A6A
0x1a68  leave.s  loc_1AC7
0x1a6a  rethrow
0x1a6c  pop
0x1a6d  leave.s  loc_1AC7
0x1a6f  ldloc.0
0x1a70  ldc.i4   0x4000014
0x1a75  ldstr    aUninstallhelpi// "UninstallHelpIndexesAction.ProgressMess"...
0x1a7a  ldc.i4.0
0x1a7b  newarr   [mscorlib]System.Object
0x1a80  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x1a85  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ExternalInstallEventHandler::Handle(int32, string)
0x1a8a  pop
0x1a8b  ldloc.2
0x1a8c  callvirt instance bool [ISWrapper]Microsoft.Crm.Tools.ISWrapper.IAdminIndexServer::IsRunning()
0x1a91  brfalse.s loc_1A9B
0x1a93  ldc.i4.1
0x1a94  stloc.1
0x1a95  ldloc.2
0x1a96  callvirt instance void [ISWrapper]Microsoft.Crm.Tools.ISWrapper.IAdminIndexServer::Stop()
0x1a9b  ldloc.2
0x1a9c  ldarg.0
0x1a9d  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.UninstallHelpIndexesAction::installer
0x1aa2  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_CatalogName()
0x1aa7  ldc.i4.1
0x1aa8  callvirt instance void [ISWrapper]Microsoft.Crm.Tools.ISWrapper.IAdminIndexServer::RemoveCatalog(string, bool)
0x1aad  ldloc.1
0x1aae  brfalse.s loc_1AB6
0x1ab0  ldloc.2
0x1ab1  callvirt instance void [ISWrapper]Microsoft.Crm.Tools.ISWrapper.IAdminIndexServer::Start()
0x1ab6  ldloc.0
0x1ab7  ldc.i4   0x6000000
0x1abc  ldstr    asc_18D5A// ""
0x1ac1  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ExternalInstallEventHandler::Handle(int32, string)
0x1ac6  pop
0x1ac7  ret
```
