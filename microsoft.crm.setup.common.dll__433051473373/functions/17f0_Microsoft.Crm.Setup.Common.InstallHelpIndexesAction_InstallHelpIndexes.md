# Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::InstallHelpIndexes

- ea: `0x17f0`
- end: `0x19a0`
- name: `Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::InstallHelpIndexes`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17c0`

## callees

- `0xff0`
- `0x14c0`
- `0x14d0`
- `0x14e0`
- `0x14f0`
- `0x1500`
- `0x1510`
- `0x17f0`

## string_xrefs

- `0x184f`: `OpenSubKey.Failed`
- `0x18b0`: `InstallHelpIndexesAction.ProgressMessage`

## pseudocode

```c

```

## disassembly

```asm
0x17f0  ldarg.0
0x17f1  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::installer
0x17f6  ldarg.1
0x17f7  ldarg.0
0x17f8  call     instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ActionWithProgress::get_ProgressStart()
0x17fd  ldarg.0
0x17fe  call     instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ActionWithProgress::get_AllocatedProgress()
0x1803  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ExternalInstallEventHandler::.ctor(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource, class [mscorlib]System.Collections.IDictionary, int32, int32)
0x1808  stloc.0
0x1809  ldc.i4.0
0x180a  stloc.1
0x180b  ldc.i4.0
0x180c  stloc.2
0x180d  ldnull
0x180e  stloc.3
0x180f  ldarg.0
0x1810  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::installer
0x1815  callvirt instance bool Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_IsCurrentUser()
0x181a  brfalse.s loc_1835
0x181c  call     class [mscorlib]Microsoft.Win32.RegistryKey [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.RegHive::get_CurrentUser()
0x1821  ldarg.0
0x1822  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::installer
0x1827  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_RegKeyPath()
0x182c  ldc.i4.1
0x182d  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x1832  stloc.3
0x1833  br.s     loc_184C
0x1835  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x183a  ldarg.0
0x183b  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::installer
0x1840  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_RegKeyPath()
0x1845  ldc.i4.1
0x1846  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x184b  stloc.3
0x184c  ldloc.3
0x184d  brtrue.s loc_1873
0x184f  ldstr    aOpensubkeyFail// "OpenSubKey.Failed"
0x1854  ldc.i4.1
0x1855  newarr   [mscorlib]System.Object
0x185a  dup
0x185b  ldc.i4.0
0x185c  ldarg.0
0x185d  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::installer
0x1862  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_RegKeyPath()
0x1867  stelem.ref
0x1868  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x186d  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string)
0x1872  throw
0x1873  newobj   instance void [ISWrapper]Microsoft.Crm.Tools.ISWrapper.AdminIndexServerClass::.ctor()
0x1878  stloc.s  4
0x187a  ldloc.s  4
0x187c  ldarg.0
0x187d  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::installer
0x1882  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_CatalogName()
0x1887  callvirt instance object [ISWrapper]Microsoft.Crm.Tools.ISWrapper.IAdminIndexServer::GetCatalogByName(string)
0x188c  pop
0x188d  ldc.i4.1
0x188e  stloc.2
0x188f  leave.s  loc_18AA
0x1891  stloc.s  6
0x1893  ldc.i4   0x490
0x1898  ldloc.s  6
0x189a  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x189f  call     int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::Win32ErrorFromHResult(int32)
0x18a4  beq.s    loc_18A8
0x18a6  rethrow
0x18a8  leave.s  loc_18AA
0x18aa  ldloc.0
0x18ab  ldc.i4   0x4000014
0x18b0  ldstr    aInstallhelpind_0// "InstallHelpIndexesAction.ProgressMessag"...
0x18b5  ldc.i4.0
0x18b6  newarr   [mscorlib]System.Object
0x18bb  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x18c0  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ExternalInstallEventHandler::Handle(int32, string)
0x18c5  pop
0x18c6  ldloc.s  4
0x18c8  callvirt instance bool [ISWrapper]Microsoft.Crm.Tools.ISWrapper.IAdminIndexServer::IsRunning()
0x18cd  brfalse.s loc_18D8
0x18cf  ldc.i4.1
0x18d0  stloc.1
0x18d1  ldloc.s  4
0x18d3  callvirt instance void [ISWrapper]Microsoft.Crm.Tools.ISWrapper.IAdminIndexServer::Stop()
0x18d8  ldloc.2
0x18d9  brfalse.s loc_18EE
0x18db  ldloc.s  4
0x18dd  ldarg.0
0x18de  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::installer
0x18e3  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_CatalogName()
0x18e8  ldc.i4.1
0x18e9  callvirt instance void [ISWrapper]Microsoft.Crm.Tools.ISWrapper.IAdminIndexServer::RemoveCatalog(string, bool)
0x18ee  ldloc.s  4
0x18f0  ldarg.0
0x18f1  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::installer
0x18f6  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_CatalogName()
0x18fb  ldarg.0
0x18fc  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::installer
0x1901  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_CatalogPath()
0x1906  callvirt instance object [ISWrapper]Microsoft.Crm.Tools.ISWrapper.IAdminIndexServer::AddCatalog(string, string)
0x190b  castclass [ISWrapper]Microsoft.Crm.Tools.ISWrapper.CatAdm
0x1910  stloc.s  5
0x1912  ldarg.0
0x1913  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::installer
0x1918  callvirt instance class [System]System.Collections.Specialized.StringCollection Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_ContentPaths()
0x191d  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x1922  stloc.s  7
0x1924  br.s     loc_193C
0x1926  ldloc.s  7
0x1928  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x192d  stloc.s  8
0x192f  ldloc.s  5
0x1931  ldloc.s  8
0x1933  ldc.i4.0
0x1934  ldnull
0x1935  ldnull
0x1936  callvirt instance object [ISWrapper]Microsoft.Crm.Tools.ISWrapper.ICatAdm::AddScope(string, bool, object, object)
0x193b  pop
0x193c  ldloc.s  7
0x193e  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x1943  brtrue.s loc_1926
0x1945  leave.s  loc_195C
0x1947  ldloc.s  7
0x1949  isinst   [mscorlib]System.IDisposable
0x194e  stloc.s  9
0x1950  ldloc.s  9
0x1952  brfalse.s loc_195B
0x1954  ldloc.s  9
0x1956  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x195b  endfinally
0x195c  ldloc.1
0x195d  brfalse.s loc_1966
0x195f  ldloc.s  4
0x1961  callvirt instance void [ISWrapper]Microsoft.Crm.Tools.ISWrapper.IAdminIndexServer::Start()
0x1966  ldloc.3
0x1967  ldarg.0
0x1968  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::installer
0x196d  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_RegValueName()
0x1972  ldarg.0
0x1973  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::installer
0x1978  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_CatalogName()
0x197d  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1982  ldloc.0
0x1983  ldc.i4   0x6000000
0x1988  ldstr    asc_18D5A// ""
0x198d  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ExternalInstallEventHandler::Handle(int32, string)
0x1992  pop
0x1993  leave.s  loc_199F
0x1995  ldloc.3
0x1996  brfalse.s loc_199E
0x1998  ldloc.3
0x1999  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::Close()
0x199e  endfinally
0x199f  ret
```
