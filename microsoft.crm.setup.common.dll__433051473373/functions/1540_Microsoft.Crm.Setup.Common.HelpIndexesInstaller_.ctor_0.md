# Microsoft.Crm.Setup.Common.HelpIndexesInstaller::.ctor_0

- ea: `0x1540`
- end: `0x161d`
- name: `Microsoft.Crm.Setup.Common.HelpIndexesInstaller::.ctor_0`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1520`

## callees

- `0xff0`
- `0x1540`
- `0x1640`
- `0x1680`
- `0x1710`
- `0x1750`

## string_xrefs

- `0x1551`: `HelpIndexesInstaller`
- `0x160c`: `HelpIndexesInstaller`
- `0x15d8`: `InstallType not supported: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1540  ldarg.0
0x1541  ldarg.1
0x1542  call     instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::.ctor(class [mscorlib]System.Collections.IDictionary)
0x1547  ldtoken  Microsoft.Crm.Setup.Common.HelpIndexesInstaller
0x154c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1551  ldstr    aHelpindexesins// "HelpIndexesInstaller"
0x1556  ldc.i4.0
0x1557  newarr   [mscorlib]System.Object
0x155c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteMethodEntry(class [mscorlib]System.Type, string, object[])
0x1561  ldarg.0
0x1562  ldarg.2
0x1563  stfld    class Microsoft.Crm.Setup.Common.HelpIndexesConfig Microsoft.Crm.Setup.Common.HelpIndexesInstaller::config
0x1568  ldarg.0
0x1569  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer/InstallerDescription [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_Description()
0x156e  ldarg.0
0x156f  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1574  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1579  ldstr    aProgressmessag// ".ProgressMessage"
0x157e  call     string [mscorlib]System.String::Concat(string, string)
0x1583  ldc.i4.0
0x1584  newarr   [mscorlib]System.Object
0x1589  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x158e  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer/InstallerDescription::set_ProgressMessage(string)
0x1593  ldarg.0
0x1594  ldarg.3
0x1595  stfld    valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType Microsoft.Crm.Setup.Common.HelpIndexesInstaller::_installTypeOverride
0x159a  ldarg.0
0x159b  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_Operation()
0x15a0  stloc.0
0x15a1  ldloc.0
0x15a2  ldc.i4.1
0x15a3  sub
0x15a4  switch   loc_15BB, loc_15C3, loc_15CB, loc_15FC
0x15b9  br.s     loc_15D3
0x15bb  ldarg.0
0x15bc  call     instance void Microsoft.Crm.Setup.Common.HelpIndexesInstaller::InitializeInstall()
0x15c1  br.s     loc_15FC
0x15c3  ldarg.0
0x15c4  call     instance void Microsoft.Crm.Setup.Common.HelpIndexesInstaller::InitializeUpgrade()
0x15c9  br.s     loc_15FC
0x15cb  ldarg.0
0x15cc  call     instance void Microsoft.Crm.Setup.Common.HelpIndexesInstaller::InitializeRepair()
0x15d1  br.s     loc_15FC
0x15d3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15d8  ldstr    aInstalltypeNot// "InstallType not supported: {0}"
0x15dd  ldc.i4.1
0x15de  newarr   [mscorlib]System.Object
0x15e3  dup
0x15e4  ldc.i4.0
0x15e5  ldarg.0
0x15e6  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_Operation()
0x15eb  box      [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType
0x15f0  stelem.ref
0x15f1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15f6  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15fb  throw
0x15fc  ldarg.0
0x15fd  call     instance void Microsoft.Crm.Setup.Common.HelpIndexesInstaller::InitializeUninstall()
0x1602  ldtoken  Microsoft.Crm.Setup.Common.HelpIndexesInstaller
0x1607  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x160c  ldstr    aHelpindexesins// "HelpIndexesInstaller"
0x1611  ldc.i4.0
0x1612  newarr   [mscorlib]System.Object
0x1617  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteMethodExit(class [mscorlib]System.Type, string, object[])
0x161c  ret
```
