# Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::BuildRollbackOperation

- ea: `0x169a0`
- end: `0x16b4f`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::BuildRollbackOperation`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x166f0`

## callees

- `0x14db0`
- `0x164c0`
- `0x164d0`
- `0x164e0`
- `0x164f0`
- `0x16510`
- `0x16520`
- `0x16550`
- `0x169a0`
- `0x16bf0`

## string_xrefs

- `0x16ab7`: `RegistryOperationCode.{0} is not supported`
- `0x16af4`: `Error occured while building registry rollback descriptor for Key: {0}, Value:{1} - {2}`

## pseudocode

```c

```

## disassembly

```asm
0x169a0  newobj   instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::.ctor()
0x169a5  dup
0x169a6  ldarg.0
0x169a7  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x169ac  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::set_KeyPath(string value)
0x169b1  dup
0x169b2  ldarg.0
0x169b3  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x169b8  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::set_Name(string value)
0x169bd  stloc.0
0x169be  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x169c3  ldarg.0
0x169c4  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x169c9  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x169ce  stloc.1
0x169cf  ldnull
0x169d0  stloc.2
0x169d1  ldloc.1
0x169d2  brfalse.s loc_16A0B
0x169d4  ldarg.0
0x169d5  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x169da  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x169df  brtrue.s loc_16A0B
0x169e1  ldloc.1
0x169e2  callvirt instance string[] [mscorlib]Microsoft.Win32.RegistryKey::GetValueNames()
0x169e7  ldarg.0
0x169e8  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x169ed  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x169f2  call     T0x2B000020
0x169f7  brfalse.s loc_16A0B
0x169f9  ldloc.1
0x169fa  ldarg.0
0x169fb  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x16a00  ldsfld   string [mscorlib]System.String::Empty
0x16a05  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x16a0a  stloc.2
0x16a0b  ldarg.0
0x16a0c  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x16a11  stloc.3
0x16a12  ldloc.3
0x16a13  ldc.i4.1
0x16a14  sub
0x16a15  switch   loc_16A2F, loc_16A62, loc_16A81, loc_16A9C
0x16a2a  br       loc_16AB7
0x16a2f  ldloc.1
0x16a30  brtrue.s loc_16A3E
0x16a32  ldloc.0
0x16a33  ldc.i4.4
0x16a34  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::set_Operation(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode value)
0x16a39  br       loc_16ADB
0x16a3e  ldloc.2
0x16a3f  brtrue.s loc_16A4D
0x16a41  ldloc.0
0x16a42  ldc.i4.2
0x16a43  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::set_Operation(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode value)
0x16a48  br       loc_16ADB
0x16a4d  ldloc.0
0x16a4e  ldc.i4.1
0x16a4f  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::set_Operation(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode value)
0x16a54  ldloc.0
0x16a55  ldloc.2
0x16a56  callvirt instance string [mscorlib]System.Object::ToString()
0x16a5b  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::set_Value(string value)
0x16a60  br.s     loc_16ADB
0x16a62  ldloc.1
0x16a63  brfalse.s loc_16A68
0x16a65  ldloc.2
0x16a66  brtrue.s loc_16A6C
0x16a68  ldnull
0x16a69  stloc.0
0x16a6a  br.s     loc_16ADB
0x16a6c  ldloc.0
0x16a6d  ldc.i4.1
0x16a6e  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::set_Operation(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode value)
0x16a73  ldloc.0
0x16a74  ldloc.2
0x16a75  callvirt instance string [mscorlib]System.Object::ToString()
0x16a7a  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::set_Value(string value)
0x16a7f  br.s     loc_16ADB
0x16a81  ldloc.1
0x16a82  brfalse.s loc_16A88
0x16a84  ldnull
0x16a85  stloc.0
0x16a86  br.s     loc_16ADB
0x16a88  ldloc.0
0x16a89  ldc.i4.4
0x16a8a  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::set_Operation(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode value)
0x16a8f  ldloc.0
0x16a90  ldsfld   string [mscorlib]System.String::Empty
0x16a95  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::set_Name(string value)
0x16a9a  br.s     loc_16ADB
0x16a9c  ldloc.1
0x16a9d  brtrue.s loc_16AA3
0x16a9f  ldnull
0x16aa0  stloc.0
0x16aa1  br.s     loc_16ADB
0x16aa3  ldloc.0
0x16aa4  ldc.i4.3
0x16aa5  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::set_Operation(valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode value)
0x16aaa  ldloc.0
0x16aab  ldsfld   string [mscorlib]System.String::Empty
0x16ab0  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::set_Name(string value)
0x16ab5  br.s     loc_16ADB
0x16ab7  ldstr    aRegistryoperat// "RegistryOperationCode.{0} is not suppor"...
0x16abc  ldc.i4.1
0x16abd  newarr   [mscorlib]System.Object
0x16ac2  dup
0x16ac3  ldc.i4.0
0x16ac4  ldarg.0
0x16ac5  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x16aca  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode
0x16acf  stelem.ref
0x16ad0  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x16ad5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x16ada  throw
0x16adb  leave.s  loc_16AE7
0x16add  ldloc.1
0x16ade  brfalse.s loc_16AE6
0x16ae0  ldloc.1
0x16ae1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16ae6  endfinally
0x16ae7  ldloc.0
0x16ae8  brfalse.s loc_16AF0
0x16aea  ldloc.0
0x16aeb  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.DescriptorElementBase::VerifyDescriptorConsistency()
0x16af0  leave.s  loc_16B4D
0x16af2  stloc.s  4
0x16af4  ldstr    aErrorOccuredWh_5// "Error occured while building registry r"...
0x16af9  ldc.i4.3
0x16afa  newarr   [mscorlib]System.Object
0x16aff  dup
0x16b00  ldc.i4.0
0x16b01  ldarg.0
0x16b02  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x16b07  stelem.ref
0x16b08  dup
0x16b09  ldc.i4.1
0x16b0a  ldarg.0
0x16b0b  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x16b10  stelem.ref
0x16b11  dup
0x16b12  ldc.i4.2
0x16b13  ldloc.s  4
0x16b15  callvirt instance string [mscorlib]System.Exception::get_Message()
0x16b1a  stelem.ref
0x16b1b  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x16b20  stloc.s  5
0x16b22  ldloc.s  5
0x16b24  ldstr    aFullException0// " Full exception: {0}"
0x16b29  call     string [mscorlib]System.String::Concat(string, string)
0x16b2e  ldc.i4.1
0x16b2f  newarr   [mscorlib]System.Object
0x16b34  dup
0x16b35  ldc.i4.0
0x16b36  ldloc.s  4
0x16b38  callvirt instance string [mscorlib]System.Object::ToString()
0x16b3d  stelem.ref
0x16b3e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x16b43  ldloc.s  5
0x16b45  ldloc.s  4
0x16b47  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x16b4c  throw
0x16b4d  ldloc.0
0x16b4e  ret
```
