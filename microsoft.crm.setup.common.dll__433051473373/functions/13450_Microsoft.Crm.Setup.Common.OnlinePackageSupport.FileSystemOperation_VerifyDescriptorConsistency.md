# Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::VerifyDescriptorConsistency

- ea: `0x13450`
- end: `0x1357e`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::VerifyDescriptorConsistency`
- size: `302`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x13230`
- `0x13580`

## callees

- `0x133d0`
- `0x133f0`
- `0x13420`
- `0x13450`

## pseudocode

```c

```

## disassembly

```asm
0x13450  ldarg.0
0x13451  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Operation()
0x13456  stloc.0
0x13457  ldloc.0
0x13458  ldc.i4.1
0x13459  sub
0x1345a  switch   loc_13480, loc_13480, loc_13511, loc_13480, loc_13480, loc_13480, loc_13480
0x1347b  br       loc_1355A
0x13480  ldarg.0
0x13481  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x13486  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1348b  ldc.i4.0
0x1348c  ceq
0x1348e  ldstr    a0SourceMustBeP// "{0}.Source must be provided with operat"...
0x13493  ldc.i4.2
0x13494  newarr   [mscorlib]System.Object
0x13499  dup
0x1349a  ldc.i4.0
0x1349b  ldarg.0
0x1349c  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x134a1  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x134a6  stelem.ref
0x134a7  dup
0x134a8  ldc.i4.1
0x134a9  ldarg.0
0x134aa  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Operation()
0x134af  stloc.0
0x134b0  ldloca.s 0
0x134b2  constrained. Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode
0x134b8  callvirt instance string [mscorlib]System.Object::ToString()
0x134bd  stelem.ref
0x134be  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x134c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x134c8  ldarg.0
0x134c9  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Target()
0x134ce  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x134d3  ldc.i4.0
0x134d4  ceq
0x134d6  ldstr    a0TargetMustBeP// "{0}.Target must be provided with operat"...
0x134db  ldc.i4.2
0x134dc  newarr   [mscorlib]System.Object
0x134e1  dup
0x134e2  ldc.i4.0
0x134e3  ldarg.0
0x134e4  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x134e9  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x134ee  stelem.ref
0x134ef  dup
0x134f0  ldc.i4.1
0x134f1  ldarg.0
0x134f2  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Operation()
0x134f7  stloc.0
0x134f8  ldloca.s 0
0x134fa  constrained. Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode
0x13500  callvirt instance string [mscorlib]System.Object::ToString()
0x13505  stelem.ref
0x13506  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x1350b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x13510  ret
0x13511  ldarg.0
0x13512  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Source()
0x13517  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1351c  ldc.i4.0
0x1351d  ceq
0x1351f  ldstr    a0SourceMustBeP// "{0}.Source must be provided with operat"...
0x13524  ldc.i4.2
0x13525  newarr   [mscorlib]System.Object
0x1352a  dup
0x1352b  ldc.i4.0
0x1352c  ldarg.0
0x1352d  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x13532  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x13537  stelem.ref
0x13538  dup
0x13539  ldc.i4.1
0x1353a  ldarg.0
0x1353b  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Operation()
0x13540  stloc.0
0x13541  ldloca.s 0
0x13543  constrained. Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode
0x13549  callvirt instance string [mscorlib]System.Object::ToString()
0x1354e  stelem.ref
0x1354f  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x13554  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x13559  ret
0x1355a  ldstr    aFilesystemoper// "FileSystemOperationCode.{0} is not supp"...
0x1355f  ldc.i4.1
0x13560  newarr   [mscorlib]System.Object
0x13565  dup
0x13566  ldc.i4.0
0x13567  ldarg.0
0x13568  call     instance valuetype Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::get_Operation()
0x1356d  box      Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperationCode
0x13572  stelem.ref
0x13573  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x13578  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1357d  throw
```
