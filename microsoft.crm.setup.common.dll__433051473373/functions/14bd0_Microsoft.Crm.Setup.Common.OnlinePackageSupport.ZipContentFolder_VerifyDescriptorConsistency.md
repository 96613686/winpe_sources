# Microsoft.Crm.Setup.Common.OnlinePackageSupport.ZipContentFolder::VerifyDescriptorConsistency

- ea: `0x14bd0`
- end: `0x14c2e`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.ZipContentFolder::VerifyDescriptorConsistency`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14b70`
- `0x14b90`
- `0x14bd0`
- `0x14d40`
- `0x14d60`
- `0x14db0`

## string_xrefs

- `0x14bdc`: `sourceSubFolder not loaded on {0} descriptor {1}`

## pseudocode

```c

```

## disassembly

```asm
0x14bd0  ldarg.0
0x14bd1  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.NamedDescriptorElement::VerifyDescriptorConsistency()
0x14bd6  ldarg.0
0x14bd7  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.ZipContentFolder::get_SourceSubFolder()
0x14bdc  ldstr    aSourcesubfolde// "sourceSubFolder not loaded on {0} descr"...
0x14be1  ldc.i4.2
0x14be2  newarr   [mscorlib]System.Object
0x14be7  dup
0x14be8  ldc.i4.0
0x14be9  ldarg.0
0x14bea  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x14bef  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x14bf4  stelem.ref
0x14bf5  dup
0x14bf6  ldc.i4.1
0x14bf7  ldarg.0
0x14bf8  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.NamedDescriptorElement::get_Name()
0x14bfd  stelem.ref
0x14bfe  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x14c03  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x14c08  ldarg.0
0x14c09  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.Exclusion[] Microsoft.Crm.Setup.Common.OnlinePackageSupport.ZipContentFolder::get_Exclusions()
0x14c0e  brfalse.s loc_14C2D
0x14c10  ldarg.0
0x14c11  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.Exclusion[] Microsoft.Crm.Setup.Common.OnlinePackageSupport.ZipContentFolder::get_Exclusions()
0x14c16  stloc.0
0x14c17  ldc.i4.0
0x14c18  stloc.1
0x14c19  br.s     loc_14C27
0x14c1b  ldloc.0
0x14c1c  ldloc.1
0x14c1d  ldelem.ref
0x14c1e  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.DescriptorElementBase::VerifyDescriptorConsistency()
0x14c23  ldloc.1
0x14c24  ldc.i4.1
0x14c25  add
0x14c26  stloc.1
0x14c27  ldloc.1
0x14c28  ldloc.0
0x14c29  ldlen
0x14c2a  conv.i4
0x14c2b  blt.s    loc_14C1B
0x14c2d  ret
```
