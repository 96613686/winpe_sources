# Microsoft.Crm.Setup.Common.PendingRebootValidator::InternalCheck

- ea: `0x3d00`
- end: `0x3eb7`
- name: `Microsoft.Crm.Setup.Common.PendingRebootValidator::InternalCheck`
- size: `439`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x2cd0`
- `0x3d00`
- `0x122d0`

## string_xrefs

- `0x3d0f`: `PendingFileRenameOperations`
- `0x3d98`: `Pending rename of files in system directory`
- `0x3e85`: `Microsoft Update reports pending reboot`

## pseudocode

```c

```

## disassembly

```asm
0x3d00  ldarg.1
0x3d01  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x3d06  stloc.0
0x3d07  ldc.i4.0
0x3d08  stloc.1
0x3d09  ldstr    aSystemCurrentc// "System\\CurrentControlSet\\Control\\Ses"...
0x3d0e  stloc.2
0x3d0f  ldstr    aPendingfileren// "PendingFileRenameOperations"
0x3d14  stloc.3
0x3d15  ldstr    aSoftwareMicros// "Software\\Microsoft\\Windows\\CurrentVe"...
0x3d1a  stloc.s  4
0x3d1c  ldstr    aSoftwareMicros_0// "Software\\Microsoft\\Windows\\CurrentVe"...
0x3d21  stloc.s  5
0x3d23  ldloc.0
0x3d24  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_RebootRequired()
0x3d29  stloc.1
0x3d2a  ldloc.1
0x3d2b  brtrue   loc_3DC6
0x3d30  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x3d35  ldloc.2
0x3d36  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x3d3b  stloc.s  6
0x3d3d  ldloc.s  6
0x3d3f  brfalse.s loc_3DB8
0x3d41  ldc.i4.s 0x25
0x3d43  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x3d48  stloc.s  7
0x3d4a  ldloc.s  7
0x3d4c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3d51  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x3d56  stloc.s  7
0x3d58  ldloc.s  6
0x3d5a  ldloc.3
0x3d5b  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x3d60  castclass string[]
0x3d65  stloc.s  8
0x3d67  ldloc.s  8
0x3d69  brfalse.s loc_3DB8
0x3d6b  ldloc.s  8
0x3d6d  ldlen
0x3d6e  brfalse.s loc_3DB8
0x3d70  ldloc.s  8
0x3d72  stloc.s  9
0x3d74  ldc.i4.0
0x3d75  stloc.s  0xA
0x3d77  br.s     loc_3DB0
0x3d79  ldloc.s  9
0x3d7b  ldloc.s  0xA
0x3d7d  ldelem.ref
0x3d7e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3d83  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x3d88  stloc.s  0xB
0x3d8a  ldc.i4.m1
0x3d8b  ldloc.s  0xB
0x3d8d  ldloc.s  7
0x3d8f  callvirt instance int32 [mscorlib]System.String::IndexOf(string)
0x3d94  beq.s    loc_3DAA
0x3d96  ldc.i4.1
0x3d97  stloc.1
0x3d98  ldstr    aPendingRenameO// "Pending rename of files in system direc"...
0x3d9d  ldc.i4.0
0x3d9e  newarr   [mscorlib]System.Object
0x3da3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x3da8  leave.s  loc_3DC6
0x3daa  ldloc.s  0xA
0x3dac  ldc.i4.1
0x3dad  add
0x3dae  stloc.s  0xA
0x3db0  ldloc.s  0xA
0x3db2  ldloc.s  9
0x3db4  ldlen
0x3db5  conv.i4
0x3db6  blt.s    loc_3D79
0x3db8  leave.s  loc_3DC6
0x3dba  ldloc.s  6
0x3dbc  brfalse.s loc_3DC5
0x3dbe  ldloc.s  6
0x3dc0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3dc5  endfinally
0x3dc6  ldloc.1
0x3dc7  brtrue.s loc_3E18
0x3dc9  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x3dce  ldloc.s  4
0x3dd0  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x3dd5  stloc.s  0xC
0x3dd7  ldloc.s  0xC
0x3dd9  brfalse.s loc_3E0A
0x3ddb  ldloc.s  0xC
0x3ddd  callvirt instance string[] [mscorlib]Microsoft.Win32.RegistryKey::GetValueNames()
0x3de2  stloc.s  0xD
0x3de4  ldloc.s  0xD
0x3de6  ldlen
0x3de7  brfalse.s loc_3E0A
0x3de9  ldc.i4.1
0x3dea  stloc.1
0x3deb  ldstr    aOneOrMoreEntri// "One or more entries in HKLM RunOnce reg"...
0x3df0  ldc.i4.1
0x3df1  newarr   [mscorlib]System.Object
0x3df6  dup
0x3df7  ldc.i4.0
0x3df8  ldstr    asc_19276// ", "
0x3dfd  ldloc.s  0xD
0x3dff  call     string [mscorlib]System.String::Join(string, string[])
0x3e04  stelem.ref
0x3e05  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x3e0a  leave.s  loc_3E18
0x3e0c  ldloc.s  0xC
0x3e0e  brfalse.s loc_3E17
0x3e10  ldloc.s  0xC
0x3e12  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3e17  endfinally
0x3e18  ldloc.1
0x3e19  brtrue.s loc_3E6A
0x3e1b  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x3e20  ldloc.s  5
0x3e22  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x3e27  stloc.s  0xE
0x3e29  ldloc.s  0xE
0x3e2b  brfalse.s loc_3E5C
0x3e2d  ldloc.s  0xE
0x3e2f  callvirt instance string[] [mscorlib]Microsoft.Win32.RegistryKey::GetValueNames()
0x3e34  stloc.s  0xF
0x3e36  ldloc.s  0xF
0x3e38  ldlen
0x3e39  brfalse.s loc_3E5C
0x3e3b  ldc.i4.1
0x3e3c  stloc.1
0x3e3d  ldstr    aOneOrMoreEntri_0// "One or more entries in HKLM RunOnceEx r"...
0x3e42  ldc.i4.1
0x3e43  newarr   [mscorlib]System.Object
0x3e48  dup
0x3e49  ldc.i4.0
0x3e4a  ldstr    asc_19276// ", "
0x3e4f  ldloc.s  0xF
0x3e51  call     string [mscorlib]System.String::Join(string, string[])
0x3e56  stelem.ref
0x3e57  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x3e5c  leave.s  loc_3E6A
0x3e5e  ldloc.s  0xE
0x3e60  brfalse.s loc_3E69
0x3e62  ldloc.s  0xE
0x3e64  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3e69  endfinally
0x3e6a  ldloc.1
0x3e6b  brtrue.s loc_3E95
0x3e6d  ldloc.0
0x3e6e  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_RemoteInstall()
0x3e73  brfalse.s loc_3E7C
0x3e75  ldc.i4.3
0x3e76  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x3e7b  ret
0x3e7c  call     bool Microsoft.Crm.Setup.Common.Utility.WindowsUpdateUtility::IsUpdateRebootRequired()
0x3e81  brfalse.s loc_3E95
0x3e83  ldc.i4.1
0x3e84  stloc.1
0x3e85  ldstr    aMicrosoftUpdat// "Microsoft Update reports pending reboot"
0x3e8a  ldc.i4.0
0x3e8b  newarr   [mscorlib]System.Object
0x3e90  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x3e95  ldloc.1
0x3e96  brfalse.s loc_3EB0
0x3e98  ldc.i4.1
0x3e99  ldarg.0
0x3e9a  ldstr    aPendingrebootv// "PendingRebootValidator.Warning"
0x3e9f  ldc.i4.0
0x3ea0  newarr   [mscorlib]System.Object
0x3ea5  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x3eaa  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3eaf  ret
0x3eb0  ldc.i4.0
0x3eb1  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x3eb6  ret
```
