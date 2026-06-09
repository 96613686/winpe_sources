# Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::GetClientInstallPath

- ea: `0x12f20`
- end: `0x12f7b`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::GetClientInstallPath`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x127f0`

## callees

- `0xff0`
- `0x12f20`

## string_xrefs

- `0x12f39`: `OpenSubKey.Failed`
- `0x12f58`: `InstallPath`

## pseudocode

```c

```

## disassembly

```asm
0x12f20  ldsfld   string [mscorlib]System.String::Empty
0x12f25  stloc.0
0x12f26  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x12f2b  ldstr    aSoftwareMicros_2// "SOFTWARE\\Microsoft\\MSCRMClient"
0x12f30  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x12f35  stloc.1
0x12f36  ldloc.1
0x12f37  brtrue.s loc_12F57
0x12f39  ldstr    aOpensubkeyFail// "OpenSubKey.Failed"
0x12f3e  ldc.i4.1
0x12f3f  newarr   [mscorlib]System.Object
0x12f44  dup
0x12f45  ldc.i4.0
0x12f46  ldstr    aSoftwareMicros_2// "SOFTWARE\\Microsoft\\MSCRMClient"
0x12f4b  stelem.ref
0x12f4c  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x12f51  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string)
0x12f56  throw
0x12f57  ldloc.1
0x12f58  ldstr    aInstallpath// "InstallPath"
0x12f5d  ldsfld   string [mscorlib]System.String::Empty
0x12f62  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x12f67  castclass [mscorlib]System.String
0x12f6c  stloc.0
0x12f6d  leave.s  loc_12F79
0x12f6f  ldloc.1
0x12f70  brfalse.s loc_12F78
0x12f72  ldloc.1
0x12f73  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12f78  endfinally
0x12f79  ldloc.0
0x12f7a  ret
```
