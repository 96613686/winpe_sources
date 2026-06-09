# LicenseFilesLocationCache::.cctor

- ea: `0x3ef10`
- end: `0x3f18d`
- name: `LicenseFilesLocationCache::.cctor`
- size: `637`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x3ef10`
- `0x48b50`
- `0x48b80`
- `0x48b90`
- `0x48ba0`
- `0x48bb0`

## string_xrefs

- `0x3ef40`: `CRM_Live_InstallDir`
- `0x3f0d1`: `Cannot load PidGenX.dll because the following file locations do not exist:`
- `0x3f11d`: `root = {0}, path = {1}, key = {2}`
- `0x3f160`: `and because cannot build files locations from the Registry for the following:`

## pseudocode

```c

```

## disassembly

```asm
0x3ef10  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class SearchLocation>::.ctor()
0x3ef15  stloc.0
0x3ef16  ldloc.0
0x3ef17  call     class [mscorlib]Microsoft.Win32.RegistryKey [Microsoft.Crm.Core]Microsoft.Crm.RegControl::get_CrmServerKeyHive()
0x3ef1c  call     string [Microsoft.Crm.Core]Microsoft.Crm.RegControl::get_CrmServerKeyPath()
0x3ef21  call     string [Microsoft.Crm.Core]Microsoft.Crm.RegControl::get_CrmServerInstallKeyDir()
0x3ef26  ldstr    aServerBin// "Server\\bin\\"
0x3ef2b  newobj   instance void SearchLocation::.ctor(class [mscorlib]Microsoft.Win32.RegistryKey registryKeyRoot, string mscrmRegistryKey, string installDirRegEntry, string relativePathNotDuringSetup)
0x3ef30  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class SearchLocation>::Add(var<u1>)
0x3ef35  ldloc.0
0x3ef36  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x3ef3b  ldstr    aSoftwareMicros// "Software\\Microsoft\\MSCRM Live"
0x3ef40  ldstr    aCrmLiveInstall// "CRM_Live_InstallDir"
0x3ef45  ldstr    asc_4C8CE// ""
0x3ef4a  newobj   instance void SearchLocation::.ctor(class [mscorlib]Microsoft.Win32.RegistryKey registryKeyRoot, string mscrmRegistryKey, string installDirRegEntry, string relativePathNotDuringSetup)
0x3ef4f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class SearchLocation>::Add(var<u1>)
0x3ef54  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3ef59  stloc.1
0x3ef5a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class SearchLocation>::.ctor()
0x3ef5f  stloc.2
0x3ef60  ldc.i4.0
0x3ef61  stloc.3
0x3ef62  ldstr    asc_4C8CE// ""
0x3ef67  stloc.s  4
0x3ef69  ldstr    asc_4C8CE// ""
0x3ef6e  stsfld   string LicenseFilesLocationCache::directory
0x3ef73  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetEntryAssembly()
0x3ef78  ldnull
0x3ef79  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x3ef7e  brfalse.s loc_3EFAE
0x3ef80  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetEntryAssembly()
0x3ef85  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x3ef8a  brfalse.s loc_3EFAE
0x3ef8c  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetEntryAssembly()
0x3ef91  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x3ef96  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x3ef9b  stloc.s  4
0x3ef9d  ldloc.s  4
0x3ef9f  ldstr    aServerBin// "Server\\bin\\"
0x3efa4  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3efa9  stsfld   string LicenseFilesLocationCache::directory
0x3efae  ldsfld   string LicenseFilesLocationCache::directory
0x3efb3  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x3efb8  brtrue   loc_3F072
0x3efbd  ldloc.1
0x3efbe  ldsfld   string LicenseFilesLocationCache::directory
0x3efc3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3efc8  ldloc.0
0x3efc9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class SearchLocation>::GetEnumerator()
0x3efce  stloc.s  5
0x3efd0  br       loc_3F056
0x3efd5  ldloca.s 5
0x3efd7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class SearchLocation>::get_Current()
0x3efdc  stloc.s  6
0x3efde  ldloc.s  6
0x3efe0  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey SearchLocation::get_RegistryKeyRoot()
0x3efe5  ldloc.s  6
0x3efe7  callvirt instance string SearchLocation::get_MscrmRegistryKey()
0x3efec  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x3eff1  stloc.s  7
0x3eff3  ldloc.s  7
0x3eff5  brfalse.s loc_3F00C
0x3eff7  ldloc.s  7
0x3eff9  ldloc.s  6
0x3effb  callvirt instance string SearchLocation::get_InstallDirRegEntry()
0x3f000  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x3f005  castclass [mscorlib]System.String
0x3f00a  stloc.s  4
0x3f00c  leave.s  loc_3F01A
0x3f00e  ldloc.s  7
0x3f010  brfalse.s loc_3F019
0x3f012  ldloc.s  7
0x3f014  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f019  endfinally
0x3f01a  ldloc.s  4
0x3f01c  brfalse.s loc_3F04E
0x3f01e  ldloc.s  4
0x3f020  ldloc.s  6
0x3f022  callvirt instance string SearchLocation::get_RelativePathNotDuringSetup()
0x3f027  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3f02c  stsfld   string LicenseFilesLocationCache::directory
0x3f031  ldsfld   string LicenseFilesLocationCache::directory
0x3f036  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x3f03b  brtrue.s loc_3F04A
0x3f03d  ldloc.1
0x3f03e  ldsfld   string LicenseFilesLocationCache::directory
0x3f043  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3f048  br.s     loc_3F056
0x3f04a  ldc.i4.1
0x3f04b  stloc.3
0x3f04c  leave.s  loc_3F074
0x3f04e  ldloc.2
0x3f04f  ldloc.s  6
0x3f051  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class SearchLocation>::Add(var<u1>)
0x3f056  ldloca.s 5
0x3f058  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class SearchLocation>::MoveNext()
0x3f05d  brtrue   loc_3EFD5
0x3f062  leave.s  loc_3F074
0x3f064  ldloca.s 5
0x3f066  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class SearchLocation>
0x3f06c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f071  endfinally
0x3f072  ldc.i4.1
0x3f073  stloc.3
0x3f074  ldloc.3
0x3f075  brtrue   loc_3F18C
0x3f07a  call     string [mscorlib]System.Environment::get_NewLine()
0x3f07f  stloc.s  8
0x3f081  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3f086  stloc.s  9
0x3f088  ldloc.1
0x3f089  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x3f08e  stloc.s  0xB
0x3f090  br.s     loc_3F0AF
0x3f092  ldloca.s 0xB
0x3f094  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x3f099  stloc.s  0xC
0x3f09b  ldloc.s  9
0x3f09d  ldloc.s  8
0x3f09f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3f0a4  pop
0x3f0a5  ldloc.s  9
0x3f0a7  ldloc.s  0xC
0x3f0a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3f0ae  pop
0x3f0af  ldloca.s 0xB
0x3f0b1  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x3f0b6  brtrue.s loc_3F092
0x3f0b8  leave.s  loc_3F0C8
0x3f0ba  ldloca.s 0xB
0x3f0bc  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x3f0c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f0c7  endfinally
0x3f0c8  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3f0cd  stloc.s  0xA
0x3f0cf  ldloc.s  0xA
0x3f0d1  ldstr    aCannotLoadPidg// "Cannot load PidGenX.dll because the fol"...
0x3f0d6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3f0db  pop
0x3f0dc  ldloc.s  0xA
0x3f0de  ldloc.s  9
0x3f0e0  callvirt instance string [mscorlib]System.Object::ToString()
0x3f0e5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3f0ea  pop
0x3f0eb  ldc.i4.0
0x3f0ec  ldloc.2
0x3f0ed  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class SearchLocation>::get_Count()
0x3f0f2  bge      loc_3F17A
0x3f0f7  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3f0fc  stloc.s  0xD
0x3f0fe  ldloc.2
0x3f0ff  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class SearchLocation>::GetEnumerator()
0x3f104  stloc.s  5
0x3f106  br.s     loc_3F13D
0x3f108  ldloca.s 5
0x3f10a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class SearchLocation>::get_Current()
0x3f10f  stloc.s  0xE
0x3f111  ldloc.s  0xD
0x3f113  ldloc.s  8
0x3f115  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3f11a  pop
0x3f11b  ldloc.s  0xD
0x3f11d  ldstr    aRoot0Path1Key2// "root = {0}, path = {1}, key = {2}"
0x3f122  ldloc.s  0xE
0x3f124  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey SearchLocation::get_RegistryKeyRoot()
0x3f129  ldloc.s  0xE
0x3f12b  callvirt instance string SearchLocation::get_MscrmRegistryKey()
0x3f130  ldloc.s  0xE
0x3f132  callvirt instance string SearchLocation::get_InstallDirRegEntry()
0x3f137  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object, object)
0x3f13c  pop
0x3f13d  ldloca.s 5
0x3f13f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class SearchLocation>::MoveNext()
0x3f144  brtrue.s loc_3F108
0x3f146  leave.s  loc_3F156
0x3f148  ldloca.s 5
0x3f14a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class SearchLocation>
0x3f150  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f155  endfinally
0x3f156  ldloc.s  0xA
0x3f158  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x3f15d  pop
0x3f15e  ldloc.s  0xA
0x3f160  ldstr    aAndBecauseCann// "and because cannot build files location"...
0x3f165  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3f16a  pop
0x3f16b  ldloc.s  0xA
0x3f16d  ldloc.s  0xD
0x3f16f  callvirt instance string [mscorlib]System.Object::ToString()
0x3f174  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3f179  pop
0x3f17a  ldloc.s  0xA
0x3f17c  callvirt instance string [mscorlib]System.Object::ToString()
0x3f181  ldc.i4   0x8004D243
0x3f186  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3f18b  throw
0x3f18c  ret
```
