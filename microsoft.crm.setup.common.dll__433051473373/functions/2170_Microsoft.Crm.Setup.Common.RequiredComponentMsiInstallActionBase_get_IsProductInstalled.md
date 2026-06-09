# Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_IsProductInstalled

- ea: `0x2170`
- end: `0x2207`
- name: `Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_IsProductInstalled`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1f10`

## callees

- `0x20a0`
- `0x20c0`
- `0x20e0`
- `0x2120`
- `0x2170`

## string_xrefs

- `0x219f`: `{0} ({1}) version {2} is installed.`

## pseudocode

```c

```

## disassembly

```asm
0x2170  ldc.i4.0
0x2171  stloc.0
0x2172  ldarg.0
0x2173  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_PackageUpgradeCode()
0x2178  ldc.i4.0
0x2179  ldloca.s 1
0x217b  call     bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiUtility::GetRelatedProductCode(valuetype [mscorlib]System.Guid, int32, valuetype [mscorlib]System.Guid&)
0x2180  pop
0x2181  ldloc.1
0x2182  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2187  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x218c  brfalse.s loc_2205
0x218e  ldloc.1
0x218f  ldstr    aVersionstring// "VersionString"
0x2194  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiUtility::GetProductInfo(valuetype [mscorlib]System.Guid, string)
0x2199  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x219e  stloc.2
0x219f  ldstr    a01Version2IsIn// "{0} ({1}) version {2} is installed."
0x21a4  ldc.i4.3
0x21a5  newarr   [mscorlib]System.Object
0x21aa  dup
0x21ab  ldc.i4.0
0x21ac  ldarg.0
0x21ad  callvirt instance string Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_ProductName()
0x21b2  stelem.ref
0x21b3  dup
0x21b4  ldc.i4.1
0x21b5  ldloc.1
0x21b6  box      [mscorlib]System.Guid
0x21bb  stelem.ref
0x21bc  dup
0x21bd  ldc.i4.2
0x21be  ldloc.2
0x21bf  stelem.ref
0x21c0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x21c5  ldarg.0
0x21c6  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_RequiredVersion()
0x21cb  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x21d0  ldc.i4.1
0x21d1  add
0x21d2  ldc.i4.0
0x21d3  ldc.i4.0
0x21d4  ldc.i4.0
0x21d5  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x21da  stloc.3
0x21db  ldarg.0
0x21dc  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_RequiredVersion()
0x21e1  ldloc.2
0x21e2  call     bool [mscorlib]System.Version::op_LessThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x21e7  brfalse.s loc_21F2
0x21e9  ldloc.2
0x21ea  ldloc.3
0x21eb  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x21f0  brtrue.s loc_2203
0x21f2  ldarg.0
0x21f3  callvirt instance bool Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::get_AcceptHigherMajorVersion()
0x21f8  brfalse.s loc_2205
0x21fa  ldloc.2
0x21fb  ldloc.3
0x21fc  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x2201  brfalse.s loc_2205
0x2203  ldc.i4.1
0x2204  stloc.0
0x2205  ldloc.0
0x2206  ret
```
