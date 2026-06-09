# Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::RetrieveInstalledLanguages

- ea: `0xca70`
- end: `0xcb02`
- name: `Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::RetrieveInstalledLanguages`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc920`

## callees

- `0xca70`

## pseudocode

```c

```

## disassembly

```asm
0xca70  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Version>::.ctor()
0xca75  stloc.0
0xca76  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0xca7b  ldstr    aSoftwareMicros// "Software\\Microsoft\\MSCRM\\LangPacks"
0xca80  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0xca85  stloc.1
0xca86  ldloc.1
0xca87  brfalse.s loc_CAF4
0xca89  ldloc.1
0xca8a  callvirt instance string[] [mscorlib]Microsoft.Win32.RegistryKey::GetSubKeyNames()
0xca8f  stloc.2
0xca90  ldc.i4.0
0xca91  stloc.3
0xca92  br.s     loc_CAEE
0xca94  ldloc.2
0xca95  ldloc.3
0xca96  ldelem.ref
0xca97  stloc.s  4
0xca99  ldloc.1
0xca9a  ldloc.s  4
0xca9c  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0xcaa1  stloc.s  5
0xcaa3  newobj   instance void [mscorlib]System.Version::.ctor()
0xcaa8  stloc.s  6
0xcaaa  ldloc.s  5
0xcaac  ldstr    aCrmLangpackVer// "CRM_LangPack_Version"
0xcab1  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0xcab6  callvirt instance string [mscorlib]System.Object::ToString()
0xcabb  ldloca.s 6
0xcabd  call     bool [mscorlib]System.Version::TryParse(string, class [mscorlib]System.Version&)
0xcac2  brfalse.s loc_CADC
0xcac4  ldc.i4.0
0xcac5  stloc.s  7
0xcac7  ldloc.s  4
0xcac9  ldloca.s 7
0xcacb  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0xcad0  brfalse.s loc_CADC
0xcad2  ldloc.0
0xcad3  ldloc.s  7
0xcad5  ldloc.s  6
0xcad7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Version>::set_Item(var<u1>, !!T0)
0xcadc  leave.s  loc_CAEA
0xcade  ldloc.s  5
0xcae0  brfalse.s loc_CAE9
0xcae2  ldloc.s  5
0xcae4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcae9  endfinally
0xcaea  ldloc.3
0xcaeb  ldc.i4.1
0xcaec  add
0xcaed  stloc.3
0xcaee  ldloc.3
0xcaef  ldloc.2
0xcaf0  ldlen
0xcaf1  conv.i4
0xcaf2  blt.s    loc_CA94
0xcaf4  leave.s  loc_CB00
0xcaf6  ldloc.1
0xcaf7  brfalse.s loc_CAFF
0xcaf9  ldloc.1
0xcafa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcaff  endfinally
0xcb00  ldloc.0
0xcb01  ret
```
