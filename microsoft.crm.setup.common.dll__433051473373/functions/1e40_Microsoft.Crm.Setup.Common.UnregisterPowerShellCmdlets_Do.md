# Microsoft.Crm.Setup.Common.UnregisterPowerShellCmdlets::Do

- ea: `0x1e40`
- end: `0x1ed1`
- name: `Microsoft.Crm.Setup.Common.UnregisterPowerShellCmdlets::Do`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1e40`

## string_xrefs

- `0x1e6c`: `Microsoft.Crm.PowerShell.dll`
- `0x1e9c`: `Microsoft.Crm.PowerShell.InstallLog`

## pseudocode

```c

```

## disassembly

```asm
0x1e40  ldarg.1
0x1e41  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x1e46  stloc.0
0x1e47  ldloc.0
0x1e48  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_TargetFolder()
0x1e4d  ldstr    aTools// "Tools"
0x1e52  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1e57  ldloc.0
0x1e58  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_InstallType()
0x1e5d  ldc.i4.3
0x1e5e  bne.un.s loc_1E6C
0x1e60  ldarg.0
0x1e61  ldc.i4.1
0x1e62  box      [mscorlib]System.Boolean
0x1e67  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::set_Ignorable(object)
0x1e6c  ldstr    aMicrosoftCrmPo// "Microsoft.Crm.PowerShell.dll"
0x1e71  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1e76  stloc.1
0x1e77  ldc.i4.1
0x1e78  newarr   [mscorlib]System.String
0x1e7d  dup
0x1e7e  ldc.i4.0
0x1e7f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e84  ldstr    aLogfile0// "/logfile={0}"
0x1e89  ldc.i4.1
0x1e8a  newarr   [mscorlib]System.Object
0x1e8f  dup
0x1e90  ldc.i4.0
0x1e91  ldloc.0
0x1e92  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_LogFile()
0x1e97  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x1e9c  ldstr    aMicrosoftCrmPo_0// "Microsoft.Crm.PowerShell.InstallLog"
0x1ea1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1ea6  stelem.ref
0x1ea7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1eac  stelem.ref
0x1ead  stloc.2
0x1eae  ldloc.1
0x1eaf  ldloc.2
0x1eb0  newobj   instance void [System.Configuration.Install]System.Configuration.Install.AssemblyInstaller::.ctor(string, string[])
0x1eb5  stloc.3
0x1eb6  ldloc.3
0x1eb7  ldc.i4.1
0x1eb8  callvirt instance void [System.Configuration.Install]System.Configuration.Install.AssemblyInstaller::set_UseNewContext(bool)
0x1ebd  ldloc.3
0x1ebe  ldnull
0x1ebf  callvirt instance void [System.Configuration.Install]System.Configuration.Install.Installer::Uninstall(class [mscorlib]System.Collections.IDictionary)
0x1ec4  leave.s  loc_1ED0
0x1ec6  ldloc.3
0x1ec7  brfalse.s loc_1ECF
0x1ec9  ldloc.3
0x1eca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ecf  endfinally
0x1ed0  ret
```
