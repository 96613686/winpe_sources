# Microsoft.Crm.Setup.Common.RegisterPowerShellCmdlets::Do

- ea: `0x1d70`
- end: `0x1e11`
- name: `Microsoft.Crm.Setup.Common.RegisterPowerShellCmdlets::Do`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1d70`

## string_xrefs

- `0x1d9c`: `Microsoft.Crm.PowerShell.dll`
- `0x1dcc`: `Microsoft.Crm.PowerShell.InstallLog`

## pseudocode

```c

```

## disassembly

```asm
0x1d70  ldarg.1
0x1d71  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x1d76  stloc.0
0x1d77  ldloc.0
0x1d78  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_TargetFolder()
0x1d7d  ldstr    aTools// "Tools"
0x1d82  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1d87  ldloc.0
0x1d88  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_InstallType()
0x1d8d  ldc.i4.3
0x1d8e  bne.un.s loc_1D9C
0x1d90  ldarg.0
0x1d91  ldc.i4.1
0x1d92  box      [mscorlib]System.Boolean
0x1d97  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::set_Ignorable(object)
0x1d9c  ldstr    aMicrosoftCrmPo// "Microsoft.Crm.PowerShell.dll"
0x1da1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1da6  stloc.1
0x1da7  ldc.i4.1
0x1da8  newarr   [mscorlib]System.String
0x1dad  dup
0x1dae  ldc.i4.0
0x1daf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1db4  ldstr    aLogfile0// "/logfile={0}"
0x1db9  ldc.i4.1
0x1dba  newarr   [mscorlib]System.Object
0x1dbf  dup
0x1dc0  ldc.i4.0
0x1dc1  ldloc.0
0x1dc2  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_LogFile()
0x1dc7  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x1dcc  ldstr    aMicrosoftCrmPo_0// "Microsoft.Crm.PowerShell.InstallLog"
0x1dd1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1dd6  stelem.ref
0x1dd7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1ddc  stelem.ref
0x1ddd  stloc.2
0x1dde  ldloc.1
0x1ddf  ldloc.2
0x1de0  newobj   instance void [System.Configuration.Install]System.Configuration.Install.AssemblyInstaller::.ctor(string, string[])
0x1de5  stloc.3
0x1de6  ldloc.3
0x1de7  ldc.i4.1
0x1de8  callvirt instance void [System.Configuration.Install]System.Configuration.Install.AssemblyInstaller::set_UseNewContext(bool)
0x1ded  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x1df2  stloc.s  4
0x1df4  ldloc.3
0x1df5  ldloc.s  4
0x1df7  callvirt instance void [System.Configuration.Install]System.Configuration.Install.Installer::Install(class [mscorlib]System.Collections.IDictionary)
0x1dfc  ldloc.3
0x1dfd  ldloc.s  4
0x1dff  callvirt instance void [System.Configuration.Install]System.Configuration.Install.Installer::Commit(class [mscorlib]System.Collections.IDictionary)
0x1e04  leave.s  loc_1E10
0x1e06  ldloc.3
0x1e07  brfalse.s loc_1E0F
0x1e09  ldloc.3
0x1e0a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e0f  endfinally
0x1e10  ret
```
