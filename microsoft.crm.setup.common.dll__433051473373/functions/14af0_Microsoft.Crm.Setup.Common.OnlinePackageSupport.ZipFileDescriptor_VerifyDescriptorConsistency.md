# Microsoft.Crm.Setup.Common.OnlinePackageSupport.ZipFileDescriptor::VerifyDescriptorConsistency

- ea: `0x14af0`
- end: `0x14b46`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.ZipFileDescriptor::VerifyDescriptorConsistency`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14ab0`
- `0x14ad0`
- `0x14af0`
- `0x14d40`
- `0x14d60`
- `0x14db0`

## string_xrefs

- `0x14afc`: `Source not loaded on {0} descriptor {1}`

## pseudocode

```c

```

## disassembly

```asm
0x14af0  ldarg.0
0x14af1  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.NamedDescriptorElement::VerifyDescriptorConsistency()
0x14af6  ldarg.0
0x14af7  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.ZipFileDescriptor::get_Source()
0x14afc  ldstr    aSourceNotLoade// "Source not loaded on {0} descriptor {1}"
0x14b01  ldc.i4.2
0x14b02  newarr   [mscorlib]System.Object
0x14b07  dup
0x14b08  ldc.i4.0
0x14b09  ldarg.0
0x14b0a  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x14b0f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x14b14  stelem.ref
0x14b15  dup
0x14b16  ldc.i4.1
0x14b17  ldarg.0
0x14b18  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.NamedDescriptorElement::get_Name()
0x14b1d  stelem.ref
0x14b1e  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x14b23  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x14b28  ldarg.0
0x14b29  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.ZipContentFolder[] Microsoft.Crm.Setup.Common.OnlinePackageSupport.ZipFileDescriptor::get_ZipFileFolders()
0x14b2e  stloc.0
0x14b2f  ldc.i4.0
0x14b30  stloc.1
0x14b31  br.s     loc_14B3F
0x14b33  ldloc.0
0x14b34  ldloc.1
0x14b35  ldelem.ref
0x14b36  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.DescriptorElementBase::VerifyDescriptorConsistency()
0x14b3b  ldloc.1
0x14b3c  ldc.i4.1
0x14b3d  add
0x14b3e  stloc.1
0x14b3f  ldloc.1
0x14b40  ldloc.0
0x14b41  ldlen
0x14b42  conv.i4
0x14b43  blt.s    loc_14B33
0x14b45  ret
```
