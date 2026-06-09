# Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint::VerifyDescriptorConsistency

- ea: `0x14a40`
- end: `0x14a84`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint::VerifyDescriptorConsistency`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x149e0`
- `0x14a00`
- `0x14d40`
- `0x14d60`
- `0x14db0`

## string_xrefs

- `0x14a4c`: `Location not loaded on {0} descriptor {1}`

## pseudocode

```c

```

## disassembly

```asm
0x14a40  ldarg.0
0x14a41  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.NamedDescriptorElement::VerifyDescriptorConsistency()
0x14a46  ldarg.0
0x14a47  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint::get_Location()
0x14a4c  ldstr    aLocationNotLoa// "Location not loaded on {0} descriptor {"...
0x14a51  ldc.i4.2
0x14a52  newarr   [mscorlib]System.Object
0x14a57  dup
0x14a58  ldc.i4.0
0x14a59  ldarg.0
0x14a5a  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x14a5f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x14a64  stelem.ref
0x14a65  dup
0x14a66  ldc.i4.1
0x14a67  ldarg.0
0x14a68  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.NamedDescriptorElement::get_Name()
0x14a6d  stelem.ref
0x14a6e  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x14a73  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x14a78  ldarg.0
0x14a79  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPointBackupDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint::get_BackupDescriptor()
0x14a7e  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.DescriptorElementBase::VerifyDescriptorConsistency()
0x14a83  ret
```
