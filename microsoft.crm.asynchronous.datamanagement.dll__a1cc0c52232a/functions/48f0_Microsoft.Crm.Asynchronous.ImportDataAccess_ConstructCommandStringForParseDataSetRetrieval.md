# Microsoft.Crm.Asynchronous.ImportDataAccess::ConstructCommandStringForParseDataSetRetrieval

- ea: `0x48f0`
- end: `0x4aaa`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::ConstructCommandStringForParseDataSetRetrieval`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4840`

## callees

- `0x48f0`
- `0x4e20`

## pseudocode

```c

```

## disassembly

```asm
0x48f0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x48f5  stloc.0
0x48f6  ldloc.0
0x48f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x48fc  ldstr    aSelectAImportd// "SELECT A.ImportDataId, A.{0}, A.IsExist"...
0x4901  ldc.i4.1
0x4902  newarr   [mscorlib]System.Object
0x4907  dup
0x4908  ldc.i4.0
0x4909  ldarg.s  6
0x490b  stelem.ref
0x490c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x4911  pop
0x4912  ldarg.1
0x4913  ldlen
0x4914  brfalse  loc_49DB
0x4919  ldc.i4.0
0x491a  stloc.1
0x491b  br       loc_49D2
0x4920  ldarg.1
0x4921  ldloc.1
0x4922  ldelem.ref
0x4923  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4928  brfalse  loc_49B1
0x492d  ldarg.2
0x492e  brfalse  loc_49CE
0x4933  ldarg.2
0x4934  ldlen
0x4935  conv.i4
0x4936  ldc.i4.3
0x4937  bne.un   loc_49CE
0x493c  ldarg.2
0x493d  ldc.i4.0
0x493e  ldelem.ref
0x493f  stloc.2
0x4940  ldarg.2
0x4941  ldc.i4.1
0x4942  ldelem.ref
0x4943  stloc.3
0x4944  ldarg.2
0x4945  ldc.i4.2
0x4946  ldelem.ref
0x4947  stloc.s  4
0x4949  ldloc.2
0x494a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x494f  brfalse.s loc_4962
0x4951  ldloc.3
0x4952  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4957  brfalse.s loc_4962
0x4959  ldloc.s  4
0x495b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4960  brtrue.s loc_49CE
0x4962  ldarg.0
0x4963  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x4968  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationSettings()
0x496d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_FullNameConventionCode()
0x4972  stloc.s  5
0x4974  ldloc.s  5
0x4976  ldloc.2
0x4977  ldloc.3
0x4978  ldloc.s  4
0x497a  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.FullNameGenerator::GenerateFullNameSqlClause(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.FullNameConventionCode, string, string, string)
0x497f  stloc.s  6
0x4981  ldarg.0
0x4982  ldloc.s  5
0x4984  ldarg.2
0x4985  call     instance bool Microsoft.Crm.Asynchronous.ImportDataAccess::IsValidFullNameColumnSet(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.FullNameConventionCode conventionCode, string[] fullNameColumns)
0x498a  brtrue.s loc_4993
0x498c  ldstr    asc_270F2// "''"
0x4991  stloc.s  6
0x4993  ldloc.0
0x4994  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4999  ldstr    a0_1// "{0}, "
0x499e  ldc.i4.1
0x499f  newarr   [mscorlib]System.Object
0x49a4  dup
0x49a5  ldc.i4.0
0x49a6  ldloc.s  6
0x49a8  stelem.ref
0x49a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x49ae  pop
0x49af  br.s     loc_49CE
0x49b1  ldloc.0
0x49b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x49b7  ldstr    a0_1// "{0}, "
0x49bc  ldc.i4.1
0x49bd  newarr   [mscorlib]System.Object
0x49c2  dup
0x49c3  ldc.i4.0
0x49c4  ldarg.1
0x49c5  ldloc.1
0x49c6  ldelem.ref
0x49c7  stelem.ref
0x49c8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x49cd  pop
0x49ce  ldloc.1
0x49cf  ldc.i4.1
0x49d0  add
0x49d1  stloc.1
0x49d2  ldloc.1
0x49d3  ldarg.1
0x49d4  ldlen
0x49d5  conv.i4
0x49d6  blt      loc_4920
0x49db  ldarg.s  4
0x49dd  brfalse.s loc_4A44
0x49df  ldarg.1
0x49e0  ldlen
0x49e1  conv.i4
0x49e2  ldc.i4.3
0x49e3  add
0x49e4  stloc.s  7
0x49e6  ldc.i4.0
0x49e7  stloc.s  8
0x49e9  br.s     loc_4A3D
0x49eb  ldarg.1
0x49ec  ldloc.s  8
0x49ee  ldelem.ref
0x49ef  stloc.s  9
0x49f1  ldnull
0x49f2  stloc.s  0xA
0x49f4  ldarg.s  4
0x49f6  ldloc.s  9
0x49f8  ldloca.s 0xA
0x49fa  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x49ff  brfalse.s loc_4A37
0x4a01  ldloc.s  0xA
0x4a03  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a08  brtrue.s loc_4A37
0x4a0a  ldloc.0
0x4a0b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4a10  ldstr    a0_1// "{0}, "
0x4a15  ldc.i4.1
0x4a16  newarr   [mscorlib]System.Object
0x4a1b  dup
0x4a1c  ldc.i4.0
0x4a1d  ldloc.s  0xA
0x4a1f  stelem.ref
0x4a20  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x4a25  pop
0x4a26  ldarg.s  5
0x4a28  ldloc.s  0xA
0x4a2a  ldloc.s  7
0x4a2c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4a31  ldloc.s  7
0x4a33  ldc.i4.1
0x4a34  add
0x4a35  stloc.s  7
0x4a37  ldloc.s  8
0x4a39  ldc.i4.1
0x4a3a  add
0x4a3b  stloc.s  8
0x4a3d  ldloc.s  8
0x4a3f  ldarg.1
0x4a40  ldlen
0x4a41  conv.i4
0x4a42  blt.s    loc_49EB
0x4a44  ldloc.0
0x4a45  ldloc.0
0x4a46  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x4a4b  ldc.i4.2
0x4a4c  sub
0x4a4d  ldc.i4.2
0x4a4e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0x4a53  pop
0x4a54  ldloc.0
0x4a55  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4a5a  ldstr    aFrom0AsAJoinIm// " FROM {0} as A JOIN ImportDataBase as B"...
0x4a5f  ldc.i4.2
0x4a60  newarr   [mscorlib]System.Object
0x4a65  dup
0x4a66  ldc.i4.0
0x4a67  ldarg.s  7
0x4a69  stelem.ref
0x4a6a  dup
0x4a6b  ldc.i4.1
0x4a6c  ldarg.s  0xA
0x4a6e  box      [mscorlib]System.Int32
0x4a73  stelem.ref
0x4a74  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x4a79  pop
0x4a7a  ldarg.3
0x4a7b  brfalse.s loc_4A89
0x4a7d  ldloc.0
0x4a7e  ldstr    aAndAIsexisting// " AND A.IsExistingRecord='0'"
0x4a83  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4a88  pop
0x4a89  ldloc.0
0x4a8a  ldstr    aAndASnBetween0// " AND A.SN BETWEEN {0} AND {1} ORDER BY "...
0x4a8f  ldarg.s  8
0x4a91  box      [mscorlib]System.Int64
0x4a96  ldarg.s  9
0x4a98  box      [mscorlib]System.Int64
0x4a9d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x4aa2  pop
0x4aa3  ldloc.0
0x4aa4  callvirt instance string [mscorlib]System.Object::ToString()
0x4aa9  ret
```
