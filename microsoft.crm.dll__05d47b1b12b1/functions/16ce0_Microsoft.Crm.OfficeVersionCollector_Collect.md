# Microsoft.Crm.OfficeVersionCollector::Collect

- ea: `0x16ce0`
- end: `0x16e8a`
- name: `Microsoft.Crm.OfficeVersionCollector::Collect`
- size: `426`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x16ce0`
- `0x17170`

## string_xrefs

- `0x16d3e`: `\Common\ProductVersion`
- `0x16d81`: `\Common\LanguageResources`

## pseudocode

```c

```

## disassembly

```asm
0x16ce0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x16ce5  ldstr    aSoftwareMicros// "SOFTWARE\\Microsoft\\Office"
0x16cea  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x16cef  stloc.0
0x16cf0  ldc.i4.0
0x16cf1  ldc.i4.0
0x16cf2  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32)
0x16cf7  stloc.1
0x16cf8  ldstr    aDDD02// "^\\d+\\.\\d+((\\.\\d+){0,2})$"
0x16cfd  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string)
0x16d02  stloc.2
0x16d03  ldloc.0
0x16d04  callvirt instance string[] [mscorlib]Microsoft.Win32.RegistryKey::GetSubKeyNames()
0x16d09  stloc.3
0x16d0a  ldc.i4.0
0x16d0b  stloc.s  4
0x16d0d  br       loc_16E73
0x16d12  ldloc.3
0x16d13  ldloc.s  4
0x16d15  ldelem.ref
0x16d16  stloc.s  5
0x16d18  ldloc.2
0x16d19  ldloc.s  5
0x16d1b  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x16d20  brfalse  loc_16E6D
0x16d25  ldloc.s  5
0x16d27  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x16d2c  stloc.s  7
0x16d2e  ldloc.s  7
0x16d30  ldloc.1
0x16d31  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x16d36  brfalse  loc_16E6D
0x16d3b  ldloc.0
0x16d3c  ldloc.s  5
0x16d3e  ldstr    aCommonProductv// "\\Common\\ProductVersion"
0x16d43  call     string [mscorlib]System.String::Concat(string, string)
0x16d48  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x16d4d  stloc.s  9
0x16d4f  ldloc.s  9
0x16d51  brtrue.s loc_16D58
0x16d53  leave    loc_16E6D
0x16d58  ldloc.s  9
0x16d5a  ldstr    aLastproduct// "LastProduct"
0x16d5f  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x16d64  castclass [mscorlib]System.String
0x16d69  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x16d6e  stloc.s  7
0x16d70  leave.s  loc_16D7E
0x16d72  ldloc.s  9
0x16d74  brfalse.s loc_16D7D
0x16d76  ldloc.s  9
0x16d78  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16d7d  endfinally
0x16d7e  ldloc.0
0x16d7f  ldloc.s  5
0x16d81  ldstr    aCommonLanguage// "\\Common\\LanguageResources"
0x16d86  call     string [mscorlib]System.String::Concat(string, string)
0x16d8b  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x16d90  stloc.s  0xA
0x16d92  ldloc.s  0xA
0x16d94  brtrue.s loc_16D9B
0x16d96  leave    loc_16E6D
0x16d9b  ldloc.s  0xA
0x16d9d  ldstr    aSkulanguage// "SKULanguage"
0x16da2  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x16da7  unbox.any [mscorlib]System.Int32
0x16dac  stloc.s  6
0x16dae  leave.s  loc_16DBC
0x16db0  ldloc.s  0xA
0x16db2  brfalse.s loc_16DBB
0x16db4  ldloc.s  0xA
0x16db6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16dbb  endfinally
0x16dbc  ldloc.s  7
0x16dbe  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x16dc3  ldc.i4.s 0xE
0x16dc5  bge.s    loc_16DCC
0x16dc7  ldc.i4.0
0x16dc8  stloc.s  8
0x16dca  br.s     loc_16E1A
0x16dcc  ldloc.0
0x16dcd  ldloc.s  5
0x16dcf  ldstr    aOutlook// "\\Outlook"
0x16dd4  call     string [mscorlib]System.String::Concat(string, string)
0x16dd9  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x16dde  stloc.s  0xB
0x16de0  ldloc.s  0xB
0x16de2  brtrue.s loc_16DE9
0x16de4  leave    loc_16E6D
0x16de9  ldloc.s  0xB
0x16deb  ldstr    aBitness// "Bitness"
0x16df0  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x16df5  castclass [mscorlib]System.String
0x16dfa  ldstr    aX86// "x86"
0x16dff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16e04  brtrue.s loc_16E09
0x16e06  ldc.i4.1
0x16e07  br.s     loc_16E0A
0x16e09  ldc.i4.0
0x16e0a  stloc.s  8
0x16e0c  leave.s  loc_16E1A
0x16e0e  ldloc.s  0xB
0x16e10  brfalse.s loc_16E19
0x16e12  ldloc.s  0xB
0x16e14  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16e19  endfinally
0x16e1a  ldloc.s  7
0x16e1c  stloc.1
0x16e1d  ldarg.1
0x16e1e  ldc.i4   0x84
0x16e23  ldloc.s  7
0x16e25  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x16e2a  callvirt instance void Microsoft.Crm.ISqmSession::set_Item(valuetype Microsoft.Crm.SqmDataPointId dataPointId, int32 value)
0x16e2f  ldarg.1
0x16e30  ldc.i4   0x85
0x16e35  ldloc.s  7
0x16e37  callvirt instance int32 [mscorlib]System.Version::get_Minor()
0x16e3c  callvirt instance void Microsoft.Crm.ISqmSession::set_Item(valuetype Microsoft.Crm.SqmDataPointId dataPointId, int32 value)
0x16e41  ldarg.1
0x16e42  ldc.i4   0x87
0x16e47  ldloc.s  7
0x16e49  callvirt instance int32 [mscorlib]System.Version::get_Build()
0x16e4e  callvirt instance void Microsoft.Crm.ISqmSession::set_Item(valuetype Microsoft.Crm.SqmDataPointId dataPointId, int32 value)
0x16e53  ldarg.1
0x16e54  ldc.i4   0x86
0x16e59  ldloc.s  6
0x16e5b  callvirt instance void Microsoft.Crm.ISqmSession::set_Item(valuetype Microsoft.Crm.SqmDataPointId dataPointId, int32 value)
0x16e60  ldarg.1
0x16e61  ldc.i4   0x1DD
0x16e66  ldloc.s  8
0x16e68  callvirt instance void Microsoft.Crm.ISqmSession::set_Item(valuetype Microsoft.Crm.SqmDataPointId dataPointId, int32 value)
0x16e6d  ldloc.s  4
0x16e6f  ldc.i4.1
0x16e70  add
0x16e71  stloc.s  4
0x16e73  ldloc.s  4
0x16e75  ldloc.3
0x16e76  ldlen
0x16e77  conv.i4
0x16e78  blt      loc_16D12
0x16e7d  leave.s  loc_16E89
0x16e7f  ldloc.0
0x16e80  brfalse.s loc_16E88
0x16e82  ldloc.0
0x16e83  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16e88  endfinally
0x16e89  ret
```
