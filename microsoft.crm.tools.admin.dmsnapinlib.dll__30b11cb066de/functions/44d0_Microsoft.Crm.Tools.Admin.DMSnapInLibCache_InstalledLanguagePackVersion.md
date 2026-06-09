# Microsoft.Crm.Tools.Admin.DMSnapInLibCache::InstalledLanguagePackVersion

- ea: `0x44d0`
- end: `0x4582`
- name: `Microsoft.Crm.Tools.Admin.DMSnapInLibCache::InstalledLanguagePackVersion`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x44d0`

## string_xrefs

- `0x44d0`: `Retrieving installed language pack version for language {0}`
- `0x4555`: `Language pack for language {0} was not found in the registry!`

## pseudocode

```c

```

## disassembly

```asm
0x44d0  ldstr    aRetrievingInst// "Retrieving installed language pack vers"...
0x44d5  ldc.i4.1
0x44d6  newarr   [mscorlib]System.Object
0x44db  dup
0x44dc  ldc.i4.0
0x44dd  ldarg.0
0x44de  box      [mscorlib]System.Int32
0x44e3  stelem.ref
0x44e4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteFormat(string, object[])
0x44e9  ldsfld   string [mscorlib]System.String::Empty
0x44ee  stloc.0
0x44ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x44f4  ldstr    aSoftwareMicros_1// "Software\\Microsoft\\MSCRM\\LangPacks\\"...
0x44f9  ldc.i4.1
0x44fa  newarr   [mscorlib]System.Object
0x44ff  dup
0x4500  ldc.i4.0
0x4501  ldarg.0
0x4502  box      [mscorlib]System.Int32
0x4507  stelem.ref
0x4508  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x450d  stloc.1
0x450e  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x4513  stloc.2
0x4514  ldloc.2
0x4515  ldloc.1
0x4516  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x451b  stloc.3
0x451c  ldloc.3
0x451d  brfalse.s loc_4555
0x451f  ldloc.3
0x4520  ldstr    aCrmLangpackVer// "CRM_LangPack_Version"
0x4525  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x452a  castclass [mscorlib]System.String
0x452f  stloc.0
0x4530  ldloc.3
0x4531  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::Close()
0x4536  ldstr    aVersionForLang// "Version for language pack for language "...
0x453b  ldc.i4.2
0x453c  newarr   [mscorlib]System.Object
0x4541  dup
0x4542  ldc.i4.0
0x4543  ldarg.0
0x4544  box      [mscorlib]System.Int32
0x4549  stelem.ref
0x454a  dup
0x454b  ldc.i4.1
0x454c  ldloc.0
0x454d  stelem.ref
0x454e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x4553  leave.s  loc_457A
0x4555  ldstr    aLanguagePackFo// "Language pack for language {0} was not "...
0x455a  ldc.i4.1
0x455b  newarr   [mscorlib]System.Object
0x4560  dup
0x4561  ldc.i4.0
0x4562  ldarg.0
0x4563  box      [mscorlib]System.Int32
0x4568  stelem.ref
0x4569  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x456e  leave.s  loc_457A
0x4570  ldloc.3
0x4571  brfalse.s loc_4579
0x4573  ldloc.3
0x4574  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4579  endfinally
0x457a  ldloc.2
0x457b  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::Close()
0x4580  ldloc.0
0x4581  ret
```
