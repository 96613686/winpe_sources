# Microsoft.Crm.Sandbox.SandboxAppDomain::CreatePartialTrustAppDomain

- ea: `0x1640`
- end: `0x1749`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomain::CreatePartialTrustAppDomain`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xdf0`

## callees

- `0x1640`
- `0x17d0`

## pseudocode

```c

```

## disassembly

```asm
0x1640  ldc.i4.0
0x1641  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x1646  stloc.0
0x1647  ldloc.0
0x1648  ldc.i4.8
0x1649  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x164e  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x1653  pop
0x1654  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1659  ldstr    a01_0// "{0}{1}"
0x165e  ldc.i4.2
0x165f  newarr   [mscorlib]System.Object
0x1664  dup
0x1665  ldc.i4.0
0x1666  ldc.i4.3
0x1667  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x166c  stelem.ref
0x166d  dup
0x166e  ldc.i4.1
0x166f  ldc.i4.8
0x1670  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty
0x1675  stelem.ref
0x1676  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x167b  ldc.i4.0
0x167c  box      [mscorlib]System.Int32
0x1681  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1686  unbox.any [mscorlib]System.Int32
0x168b  brtrue.s loc_16EB
0x168d  ldstr    aHttpSLocalhost// "^http[s]?://(?!((localhost[:/])|(\\[.*"...
0x1692  stloc.2
0x1693  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1698  ldstr    a01_0// "{0}{1}"
0x169d  ldc.i4.2
0x169e  newarr   [mscorlib]System.Object
0x16a3  dup
0x16a4  ldc.i4.0
0x16a5  ldc.i4.3
0x16a6  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x16ab  stelem.ref
0x16ac  dup
0x16ad  ldc.i4.1
0x16ae  ldc.i4.s 9
0x16b0  box      [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerProperty
0x16b5  stelem.ref
0x16b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16bb  ldloc.2
0x16bc  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x16c1  castclass [mscorlib]System.String
0x16c6  stloc.3
0x16c7  newobj   instance void [System]System.Net.WebPermission::.ctor()
0x16cc  stloc.s  4
0x16ce  ldloc.s  4
0x16d0  ldc.i4.s 0x40
0x16d2  ldloc.3
0x16d3  ldc.i4   0x219
0x16d8  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x16dd  callvirt instance void [System]System.Net.WebPermission::AddPermission(valuetype [System]System.Net.NetworkAccess, class [System]System.Text.RegularExpressions.Regex)
0x16e2  ldloc.0
0x16e3  ldloc.s  4
0x16e5  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x16ea  pop
0x16eb  newobj   instance void [mscorlib]System.AppDomainSetup::.ctor()
0x16f0  stloc.1
0x16f1  ldloc.1
0x16f2  ldarg.0
0x16f3  ldfld    string Microsoft.Crm.Sandbox.SandboxAppDomain::_pluginAssemblyBase
0x16f8  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x16fd  stloc.s  5
0x16ff  ldloca.s 5
0x1701  ldstr    aB// "B"
0x1706  call     instance string [mscorlib]System.Guid::ToString(string)
0x170b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1710  callvirt instance void [mscorlib]System.AppDomainSetup::set_ApplicationBase(string)
0x1715  ldloc.1
0x1716  call     string[] [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo::GetPartialTrustAssemblyList()
0x171b  callvirt instance void [mscorlib]System.AppDomainSetup::set_PartialTrustVisibleAssemblies(string[])
0x1720  ldstr    aSandboxAppdoma// "Sandbox AppDomain: "
0x1725  ldarga.s 1
0x1727  ldstr    aB// "B"
0x172c  call     instance string [mscorlib]System.Guid::ToString(string)
0x1731  call     string [mscorlib]System.String::Concat(string, string)
0x1736  ldnull
0x1737  ldloc.1
0x1738  ldloc.0
0x1739  call     class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Security.Policy.StrongName> Microsoft.Crm.Sandbox.SandboxAppDomain::get_TrustedAssemblies()
0x173e  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Security.Policy.StrongName>::ToArray()
0x1743  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::CreateDomain(string, class [mscorlib]System.Security.Policy.Evidence, class [mscorlib]System.AppDomainSetup, class [mscorlib]System.Security.PermissionSet, class [mscorlib]System.Security.Policy.StrongName[])
0x1748  ret
```
