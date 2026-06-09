# Microsoft.Crm.Setup.Common.HelpIndexesInstaller::InitializeInstall

- ea: `0x1640`
- end: `0x1678`
- name: `Microsoft.Crm.Setup.Common.HelpIndexesInstaller::InitializeInstall`
- size: `56`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1540`
- `0x1750`

## callees

- `0x1640`
- `0x1780`
- `0x1ae0`

## pseudocode

```c

```

## disassembly

```asm
0x1640  call     bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::get_IsWindowsServer2012OrLater()
0x1645  brfalse.s loc_1653
0x1647  ldarg.0
0x1648  ldc.i4.0
0x1649  ldc.i4.s 0x5A
0x164b  newobj   instance void Microsoft.Crm.Setup.Common.InstallWindowsSearchAction::.ctor(class Microsoft.Crm.Setup.Common.HelpIndexesInstaller installer, int32 progressStart, int32 allocatedProgress)
0x1650  stloc.0
0x1651  br.s     loc_165D
0x1653  ldarg.0
0x1654  ldc.i4.0
0x1655  ldc.i4.s 0x5A
0x1657  newobj   instance void Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::.ctor(class Microsoft.Crm.Setup.Common.HelpIndexesInstaller installer, int32 progressStart, int32 allocatedProgress)
0x165c  stloc.0
0x165d  ldarg.0
0x165e  ldloc.0
0x165f  ldloc.0
0x1660  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ActionWithProgress::get_AllocatedProgress()
0x1665  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::AllocateProgress(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction, int32)
0x166a  ldarg.0
0x166b  call     instance class [mscorlib]System.Collections.IList [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_InstallActions()
0x1670  ldloc.0
0x1671  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x1676  pop
0x1677  ret
```
