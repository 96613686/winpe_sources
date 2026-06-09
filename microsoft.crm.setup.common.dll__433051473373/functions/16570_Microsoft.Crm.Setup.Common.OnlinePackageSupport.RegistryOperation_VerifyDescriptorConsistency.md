# Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::VerifyDescriptorConsistency

- ea: `0x16570`
- end: `0x166e1`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::VerifyDescriptorConsistency`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x164c0`
- `0x164e0`
- `0x16510`
- `0x16540`
- `0x16570`

## string_xrefs

- `0x165a2`: `KeyPath must be provided for registry operation`
- `0x16636`: `KeyPath must be provided for registry operation`
- `0x16699`: `KeyPath must be provided for registry operation`
- `0x165d3`: `Name must be provided for registry operation`
- `0x16667`: `Name must be provided for registry operation`
- `0x16604`: `Value must be provided for registry operation`
- `0x166bd`: `RegistryOperationCode.{0} is not supported`

## pseudocode

```c

```

## disassembly

```asm
0x16570  ldarg.0
0x16571  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x16576  stloc.0
0x16577  ldloc.0
0x16578  ldc.i4.1
0x16579  sub
0x1657a  switch   loc_16594, loc_16628, loc_1668B, loc_1668B
0x1658f  br       loc_166BD
0x16594  ldarg.0
0x16595  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x1659a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1659f  ldc.i4.0
0x165a0  ceq
0x165a2  ldstr    aKeypathMustBeP// "KeyPath must be provided for registry o"...
0x165a7  ldc.i4.1
0x165a8  newarr   [mscorlib]System.Object
0x165ad  dup
0x165ae  ldc.i4.0
0x165af  ldarg.0
0x165b0  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x165b5  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode
0x165ba  stelem.ref
0x165bb  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x165c0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x165c5  ldarg.0
0x165c6  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x165cb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x165d0  ldc.i4.0
0x165d1  ceq
0x165d3  ldstr    aNameMustBeProv_0// "Name must be provided for registry oper"...
0x165d8  ldc.i4.1
0x165d9  newarr   [mscorlib]System.Object
0x165de  dup
0x165df  ldc.i4.0
0x165e0  ldarg.0
0x165e1  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x165e6  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode
0x165eb  stelem.ref
0x165ec  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x165f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x165f6  ldarg.0
0x165f7  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Value()
0x165fc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16601  ldc.i4.0
0x16602  ceq
0x16604  ldstr    aValueMustBePro// "Value must be provided for registry ope"...
0x16609  ldc.i4.1
0x1660a  newarr   [mscorlib]System.Object
0x1660f  dup
0x16610  ldc.i4.0
0x16611  ldarg.0
0x16612  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x16617  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode
0x1661c  stelem.ref
0x1661d  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x16622  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x16627  ret
0x16628  ldarg.0
0x16629  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x1662e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16633  ldc.i4.0
0x16634  ceq
0x16636  ldstr    aKeypathMustBeP// "KeyPath must be provided for registry o"...
0x1663b  ldc.i4.1
0x1663c  newarr   [mscorlib]System.Object
0x16641  dup
0x16642  ldc.i4.0
0x16643  ldarg.0
0x16644  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x16649  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode
0x1664e  stelem.ref
0x1664f  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x16654  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x16659  ldarg.0
0x1665a  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x1665f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16664  ldc.i4.0
0x16665  ceq
0x16667  ldstr    aNameMustBeProv_0// "Name must be provided for registry oper"...
0x1666c  ldc.i4.1
0x1666d  newarr   [mscorlib]System.Object
0x16672  dup
0x16673  ldc.i4.0
0x16674  ldarg.0
0x16675  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x1667a  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode
0x1667f  stelem.ref
0x16680  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x16685  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1668a  ret
0x1668b  ldarg.0
0x1668c  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x16691  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16696  ldc.i4.0
0x16697  ceq
0x16699  ldstr    aKeypathMustBeP// "KeyPath must be provided for registry o"...
0x1669e  ldc.i4.1
0x1669f  newarr   [mscorlib]System.Object
0x166a4  dup
0x166a5  ldc.i4.0
0x166a6  ldarg.0
0x166a7  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x166ac  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode
0x166b1  stelem.ref
0x166b2  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x166b7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x166bc  ret
0x166bd  ldstr    aRegistryoperat// "RegistryOperationCode.{0} is not suppor"...
0x166c2  ldc.i4.1
0x166c3  newarr   [mscorlib]System.Object
0x166c8  dup
0x166c9  ldc.i4.0
0x166ca  ldarg.0
0x166cb  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x166d0  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode
0x166d5  stelem.ref
0x166d6  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x166db  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x166e0  throw
```
