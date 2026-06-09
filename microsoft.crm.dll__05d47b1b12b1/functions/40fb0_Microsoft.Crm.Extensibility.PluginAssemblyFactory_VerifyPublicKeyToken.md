# Microsoft.Crm.Extensibility.PluginAssemblyFactory::VerifyPublicKeyToken

- ea: `0x40fb0`
- end: `0x41077`
- name: `Microsoft.Crm.Extensibility.PluginAssemblyFactory::VerifyPublicKeyToken`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x40fb0`
- `0x41240`

## string_xrefs

- `0x41057`: `Public key token {0} is not found in allow list.`

## pseudocode

```c

```

## disassembly

```asm
0x40fb0  ldarg.0
0x40fb1  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x40fb6  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x40fbb  callvirt instance unsigned int8[] [mscorlib]System.Reflection.AssemblyName::GetPublicKeyToken()
0x40fc0  stloc.0
0x40fc1  ldloc.0
0x40fc2  brfalse.s loc_40FC8
0x40fc4  ldloc.0
0x40fc5  ldlen
0x40fc6  brtrue.s loc_40FD9
0x40fc8  ldc.i4   0x8004416C
0x40fcd  ldc.i4.0
0x40fce  newarr   [mscorlib]System.Object
0x40fd3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x40fd8  throw
0x40fd9  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x40fde  brfalse  loc_41076
0x40fe3  ldc.i4.0
0x40fe4  stloc.1
0x40fe5  ldloc.0
0x40fe6  call     string Microsoft.Crm.Extensibility.PluginAssemblyFactory::FormatPublicKeyToken(unsigned int8[] publicKeyToken)
0x40feb  stloc.2
0x40fec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x40ff1  ldstr    a01_1// "{0}\\{1}"
0x40ff6  ldc.i4.2
0x40ff7  newarr   [mscorlib]System.Object
0x40ffc  dup
0x40ffd  ldc.i4.0
0x40ffe  call     string [Microsoft.Crm.Core]Microsoft.Crm.RegControl::get_CrmClientKeyPath()
0x41003  stelem.ref
0x41004  dup
0x41005  ldc.i4.1
0x41006  ldstr    aAllowlist// "AllowList"
0x4100b  stelem.ref
0x4100c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x41011  stloc.3
0x41012  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::CurrentUser
0x41017  ldloc.3
0x41018  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x4101d  stloc.s  4
0x4101f  ldloc.s  4
0x41021  brfalse.s loc_41041
0x41023  ldloc.s  4
0x41025  ldloc.2
0x41026  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x4102b  stloc.s  5
0x4102d  ldloc.s  5
0x4102f  brfalse.s loc_41033
0x41031  ldc.i4.1
0x41032  stloc.1
0x41033  leave.s  loc_4104F
0x41035  ldloc.s  5
0x41037  brfalse.s loc_41040
0x41039  ldloc.s  5
0x4103b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41040  endfinally
0x41041  leave.s  loc_4104F
0x41043  ldloc.s  4
0x41045  brfalse.s loc_4104E
0x41047  ldloc.s  4
0x41049  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4104e  endfinally
0x4104f  ldloc.1
0x41050  brtrue.s loc_41076
0x41052  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x41057  ldstr    aPublicKeyToken// "Public key token {0} is not found in al"...
0x4105c  ldc.i4.1
0x4105d  newarr   [mscorlib]System.Object
0x41062  dup
0x41063  ldc.i4.0
0x41064  ldloc.2
0x41065  stelem.ref
0x41066  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4106b  ldc.i4   0x80044191
0x41070  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x41075  throw
0x41076  ret
```
