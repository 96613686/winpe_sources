# Microsoft.Crm.Setup.Common.HelpIndexesInstaller::InitializeUpgrade

- ea: `0x1680`
- end: `0x170b`
- name: `Microsoft.Crm.Setup.Common.HelpIndexesInstaller::InitializeUpgrade`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1540`

## callees

- `0x13e0`
- `0x1680`
- `0x1780`
- `0x19b0`
- `0x1ae0`

## pseudocode

```c

```

## disassembly

```asm
0x1680  call     bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::get_IsWindowsServer2012OrLater()
0x1685  brfalse.s loc_16AC
0x1687  ldarg.0
0x1688  ldc.i4.0
0x1689  ldc.i4.s 0x64
0x168b  newobj   instance void Microsoft.Crm.Setup.Common.InstallWindowsSearchAction::.ctor(class Microsoft.Crm.Setup.Common.HelpIndexesInstaller installer, int32 progressStart, int32 allocatedProgress)
0x1690  stloc.0
0x1691  ldarg.0
0x1692  ldloc.0
0x1693  ldloc.0
0x1694  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ActionWithProgress::get_AllocatedProgress()
0x1699  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::AllocateProgress(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction, int32)
0x169e  ldarg.0
0x169f  call     instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_InstallActions()
0x16a4  ldloc.0
0x16a5  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x16aa  pop
0x16ab  ret
0x16ac  ldarg.0
0x16ad  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesConfig Microsoft.Crm.Setup.Common.HelpIndexesInstaller::config
0x16b2  brfalse.s loc_16C1
0x16b4  ldarg.0
0x16b5  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesConfig Microsoft.Crm.Setup.Common.HelpIndexesInstaller::config
0x16ba  callvirt instance bool Microsoft.Crm.Setup.Common.HelpIndexesConfig::get_IsLightClient()
0x16bf  brtrue.s loc_16E6
0x16c1  ldarg.0
0x16c2  ldc.i4.0
0x16c3  ldc.i4.s 0x64
0x16c5  newobj   instance void Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::.ctor(class Microsoft.Crm.Setup.Common.HelpIndexesInstaller installer, int32 progressStart, int32 allocatedProgress)
0x16ca  stloc.1
0x16cb  ldarg.0
0x16cc  ldloc.1
0x16cd  ldloc.1
0x16ce  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ActionWithProgress::get_AllocatedProgress()
0x16d3  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::AllocateProgress(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction, int32)
0x16d8  ldarg.0
0x16d9  call     instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_InstallActions()
0x16de  ldloc.1
0x16df  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x16e4  pop
0x16e5  ret
0x16e6  ldarg.0
0x16e7  ldc.i4.0
0x16e8  ldc.i4.s 0x64
0x16ea  newobj   instance void Microsoft.Crm.Setup.Common.UninstallHelpIndexesAction::.ctor(class Microsoft.Crm.Setup.Common.HelpIndexesInstaller installer, int32 progressStart, int32 allocatedProgress)
0x16ef  stloc.2
0x16f0  ldarg.0
0x16f1  ldloc.2
0x16f2  ldloc.2
0x16f3  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ActionWithProgress::get_AllocatedProgress()
0x16f8  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::AllocateProgress(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction, int32)
0x16fd  ldarg.0
0x16fe  call     instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_InstallActions()
0x1703  ldloc.2
0x1704  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x1709  pop
0x170a  ret
```
