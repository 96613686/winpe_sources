# Microsoft.Crm.Tools.Admin.ProvisioningPath::GetBasePath

- ea: `0xa480`
- end: `0xa4e3`
- name: `Microsoft.Crm.Tools.Admin.ProvisioningPath::GetBasePath`
- size: `99`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xa550`
- `0xa580`
- `0xa5a0`
- `0xa5c0`
- `0xec10`
- `0x10c10`

## callees

- `0xa480`
- `0xa4f0`
- `0xa5e0`
- `0xa640`

## pseudocode

```c

```

## disassembly

```asm
0xa480  ldsfld   string [mscorlib]System.String::Empty
0xa485  stloc.0
0xa486  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0xa48b  call     string Microsoft.Crm.Tools.Admin.ProvisioningPath::get_ServerPathSubKey()
0xa490  ldc.i4.0
0xa491  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0xa496  stloc.1
0xa497  ldloc.1
0xa498  brfalse.s loc_A4B0
0xa49a  ldloc.1
0xa49b  call     string Microsoft.Crm.Tools.Admin.ProvisioningPath::get_InstallRegistryValue()
0xa4a0  ldsfld   string [mscorlib]System.String::Empty
0xa4a5  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0xa4aa  castclass [mscorlib]System.String
0xa4af  stloc.0
0xa4b0  leave.s  loc_A4BC
0xa4b2  ldloc.1
0xa4b3  brfalse.s loc_A4BB
0xa4b5  ldloc.1
0xa4b6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa4bb  endfinally
0xa4bc  ldloc.0
0xa4bd  ldstr    aLangpacks// "LangPacks"
0xa4c2  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xa4c7  ldarg.0
0xa4c8  brtrue.s loc_A4D1
0xa4ca  call     int32 Microsoft.Crm.Tools.Admin.ProvisioningPath::InstalledLanguageCode()
0xa4cf  starg.s  0
0xa4d1  ldarga.s 0
0xa4d3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa4d8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa4dd  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xa4e2  ret
```
