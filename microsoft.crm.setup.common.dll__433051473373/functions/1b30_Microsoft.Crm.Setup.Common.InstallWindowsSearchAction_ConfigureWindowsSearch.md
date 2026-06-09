# Microsoft.Crm.Setup.Common.InstallWindowsSearchAction::ConfigureWindowsSearch

- ea: `0x1b30`
- end: `0x1c51`
- name: `Microsoft.Crm.Setup.Common.InstallWindowsSearchAction::ConfigureWindowsSearch`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1b20`

## callees

- `0xff0`
- `0x14c0`
- `0x14d0`
- `0x1500`
- `0x1b30`
- `0x1c60`

## string_xrefs

- `0x1bfa`: `OpenSubKey.Failed`

## pseudocode

```c

```

## disassembly

```asm
0x1b30  ldarg.0
0x1b31  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallWindowsSearchAction::installer
0x1b36  ldarg.1
0x1b37  ldarg.0
0x1b38  call     instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ActionWithProgress::get_ProgressStart()
0x1b3d  ldarg.0
0x1b3e  call     instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ActionWithProgress::get_AllocatedProgress()
0x1b43  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ExternalInstallEventHandler::.ctor(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource, class [mscorlib]System.Collections.IDictionary, int32, int32)
0x1b48  stloc.0
0x1b49  ldc.i4.0
0x1b4a  stloc.1
0x1b4b  ldc.i4.0
0x1b4c  stloc.2
0x1b4d  nop
0x1b4e  ldarg.0
0x1b4f  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallWindowsSearchAction::installer
0x1b54  callvirt instance class [System]System.Collections.Specialized.StringCollection Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_ContentPaths()
0x1b59  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x1b5e  stloc.s  4
0x1b60  br.s     loc_1B73
0x1b62  ldloc.s  4
0x1b64  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x1b69  call     string Microsoft.Crm.Setup.Common.InstallWindowsSearchAction::GetIndexPath(string contentPath)
0x1b6e  call     void [Microsoft.Crm.Setup.Common.Interop]Microsoft.Crm.Setup.Common.Utility.WindowsSearchUtility::AddIndex(string)
0x1b73  ldloc.s  4
0x1b75  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x1b7a  brtrue.s loc_1B62
0x1b7c  leave.s  loc_1B93
0x1b7e  ldloc.s  4
0x1b80  isinst   [mscorlib]System.IDisposable
0x1b85  stloc.s  5
0x1b87  ldloc.s  5
0x1b89  brfalse.s loc_1B92
0x1b8b  ldloc.s  5
0x1b8d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b92  endfinally
0x1b93  ldc.i4.1
0x1b94  stloc.2
0x1b95  leave.s  loc_1BB7
0x1b97  pop
0x1b98  ldloc.1
0x1b99  ldc.i4.1
0x1b9a  add
0x1b9b  stloc.1
0x1b9c  ldloc.1
0x1b9d  ldc.i4.3
0x1b9e  ble.s    loc_1BA2
0x1ba0  rethrow
0x1ba2  ldc.r8   5.0
0x1bab  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1bb0  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0x1bb5  leave.s  loc_1BB7
0x1bb7  ldloc.1
0x1bb8  ldc.i4.3
0x1bb9  bge.s    loc_1BBE
0x1bbb  ldloc.2
0x1bbc  brfalse.s loc_1B4D
0x1bbe  ldstr    asc_18E1C// ";"
0x1bc3  ldarg.0
0x1bc4  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallWindowsSearchAction::installer
0x1bc9  callvirt instance class [System]System.Collections.Specialized.StringCollection Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_ContentPaths()
0x1bce  call     T0x2B000002
0x1bd3  call     T0x2B000003
0x1bd8  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x1bdd  stloc.3
0x1bde  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x1be3  ldarg.0
0x1be4  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallWindowsSearchAction::installer
0x1be9  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_RegKeyPath()
0x1bee  ldc.i4.1
0x1bef  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x1bf4  stloc.s  6
0x1bf6  ldloc.s  6
0x1bf8  brtrue.s loc_1C1E
0x1bfa  ldstr    aOpensubkeyFail// "OpenSubKey.Failed"
0x1bff  ldc.i4.1
0x1c00  newarr   [mscorlib]System.Object
0x1c05  dup
0x1c06  ldc.i4.0
0x1c07  ldarg.0
0x1c08  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallWindowsSearchAction::installer
0x1c0d  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_RegKeyPath()
0x1c12  stelem.ref
0x1c13  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x1c18  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string)
0x1c1d  throw
0x1c1e  ldloc.s  6
0x1c20  ldarg.0
0x1c21  ldfld    class Microsoft.Crm.Setup.Common.HelpIndexesInstaller Microsoft.Crm.Setup.Common.InstallWindowsSearchAction::installer
0x1c26  callvirt instance string Microsoft.Crm.Setup.Common.HelpIndexesInstaller::get_RegValueName()
0x1c2b  ldloc.3
0x1c2c  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x1c31  leave.s  loc_1C3F
0x1c33  ldloc.s  6
0x1c35  brfalse.s loc_1C3E
0x1c37  ldloc.s  6
0x1c39  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c3e  endfinally
0x1c3f  ldloc.0
0x1c40  ldc.i4   0x6000000
0x1c45  ldstr    asc_18D5A// ""
0x1c4a  callvirt instance int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ExternalInstallEventHandler::Handle(int32, string)
0x1c4f  pop
0x1c50  ret
```
