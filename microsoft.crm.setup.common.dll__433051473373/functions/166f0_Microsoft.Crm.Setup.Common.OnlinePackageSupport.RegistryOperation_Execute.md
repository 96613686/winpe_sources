# Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::Execute

- ea: `0x166f0`
- end: `0x167b4`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::Execute`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x15990`
- `0x16190`

## callees

- `0x164c0`
- `0x164e0`
- `0x16510`
- `0x166f0`
- `0x167c0`
- `0x168a0`
- `0x16910`
- `0x16970`
- `0x169a0`

## string_xrefs

- `0x16738`: `RegistryOperationCode.{0} is not supported`
- `0x1675f`: `Error occured while processing registry key {0}, Value: {1} - {2}`

## pseudocode

```c

```

## disassembly

```asm
0x166f0  ldarg.0
0x166f1  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::BuildRollbackOperation()
0x166f6  stloc.0
0x166f7  ldarg.0
0x166f8  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x166fd  stloc.1
0x166fe  ldloc.1
0x166ff  ldc.i4.1
0x16700  sub
0x16701  switch   loc_16718, loc_16720, loc_16728, loc_16730
0x16716  br.s     loc_16738
0x16718  ldarg.0
0x16719  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::SetRegistryValue()
0x1671e  br.s     loc_1675C
0x16720  ldarg.0
0x16721  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::RemoveRegistryValue()
0x16726  br.s     loc_1675C
0x16728  ldarg.0
0x16729  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::CreateRegistryKey()
0x1672e  br.s     loc_1675C
0x16730  ldarg.0
0x16731  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::RemoveRegistryKey()
0x16736  br.s     loc_1675C
0x16738  ldstr    aRegistryoperat// "RegistryOperationCode.{0} is not suppor"...
0x1673d  ldc.i4.1
0x1673e  newarr   [mscorlib]System.Object
0x16743  dup
0x16744  ldc.i4.0
0x16745  ldarg.0
0x16746  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Operation()
0x1674b  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperationCode
0x16750  stelem.ref
0x16751  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x16756  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1675b  throw
0x1675c  leave.s  loc_167B2
0x1675e  stloc.2
0x1675f  ldstr    aErrorOccuredWh_4// "Error occured while processing registry"...
0x16764  ldc.i4.3
0x16765  newarr   [mscorlib]System.Object
0x1676a  dup
0x1676b  ldc.i4.0
0x1676c  ldarg.0
0x1676d  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_KeyPath()
0x16772  stelem.ref
0x16773  dup
0x16774  ldc.i4.1
0x16775  ldarg.0
0x16776  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::get_Name()
0x1677b  stelem.ref
0x1677c  dup
0x1677d  ldc.i4.2
0x1677e  ldloc.2
0x1677f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x16784  stelem.ref
0x16785  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x1678a  stloc.3
0x1678b  ldloc.3
0x1678c  ldstr    aFullException0// " Full exception: {0}"
0x16791  call     string [mscorlib]System.String::Concat(string, string)
0x16796  ldc.i4.1
0x16797  newarr   [mscorlib]System.Object
0x1679c  dup
0x1679d  ldc.i4.0
0x1679e  ldloc.2
0x1679f  callvirt instance string [mscorlib]System.Object::ToString()
0x167a4  stelem.ref
0x167a5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x167aa  ldloc.3
0x167ab  ldloc.2
0x167ac  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x167b1  throw
0x167b2  ldloc.0
0x167b3  ret
```
