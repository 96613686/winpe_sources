# Microsoft.Crm.Asynchronous.ImportDataAccess::CreateParsedTable

- ea: `0x3fd0`
- end: `0x40c0`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::CreateParsedTable`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14370`

## callees

- `0x3fd0`
- `0x4540`

## string_xrefs

- `0x3fd5`: `CREATE TABLE dbo.{0} \n							(\n								SN bigint primary key,\n								IsTransformed int default 0,\n								ImportDataId uniqueidentifier,\n								IsExistingRecord bit default 0,\n								{1}0 uniqueidentifier`
- `0x4066`: `UPDATE ImportFileBase SET ParsedTableName = @parsedTableName WHERE ImportFileId = @importFileId`

## pseudocode

```c

```

## disassembly

```asm
0x3fd0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3fd5  ldstr    aCreateTableDbo_0// "CREATE TABLE dbo.{0} \r\n\t\t\t\t\t\t\t"...
0x3fda  ldc.i4.2
0x3fdb  newarr   [mscorlib]System.Object
0x3fe0  dup
0x3fe1  ldc.i4.0
0x3fe2  ldarg.1
0x3fe3  stelem.ref
0x3fe4  dup
0x3fe5  ldc.i4.1
0x3fe6  ldarg.2
0x3fe7  stelem.ref
0x3fe8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3fed  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x3ff2  stloc.0
0x3ff3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ff8  ldstr    aNvarchar0// "nvarchar({0})"
0x3ffd  ldc.i4.1
0x3ffe  newarr   [mscorlib]System.Object
0x4003  dup
0x4004  ldc.i4.0
0x4005  ldc.i4   0x1F4
0x400a  box      [mscorlib]System.Int32
0x400f  stelem.ref
0x4010  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4015  stloc.1
0x4016  ldc.i4.1
0x4017  stloc.2
0x4018  br.s     loc_404B
0x401a  ldloc.0
0x401b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4020  ldstr    a012// ",{0}{1} {2}"
0x4025  ldc.i4.3
0x4026  newarr   [mscorlib]System.Object
0x402b  dup
0x402c  ldc.i4.0
0x402d  ldarg.2
0x402e  stelem.ref
0x402f  dup
0x4030  ldc.i4.1
0x4031  ldloc.2
0x4032  box      [mscorlib]System.Int32
0x4037  stelem.ref
0x4038  dup
0x4039  ldc.i4.2
0x403a  ldloc.1
0x403b  stelem.ref
0x403c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4041  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4046  pop
0x4047  ldloc.2
0x4048  ldc.i4.1
0x4049  add
0x404a  stloc.2
0x404b  ldloc.2
0x404c  ldarg.3
0x404d  ble.s    loc_401A
0x404f  ldloc.0
0x4050  ldstr    asc_26068// ");\n"
0x4055  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x405a  pop
0x405b  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x4060  stloc.3
0x4061  ldarg.s  5
0x4063  brfalse.s loc_40A0
0x4065  ldloc.0
0x4066  ldstr    aUpdateImportfi_5// "UPDATE ImportFileBase SET ParsedTableNa"...
0x406b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4070  pop
0x4071  ldloc.3
0x4072  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x4077  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x407c  dup
0x407d  ldstr    aParsedtablenam// "@parsedTableName"
0x4082  ldarg.1
0x4083  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4088  pop
0x4089  ldstr    aImportfileid_0// "@importFileId"
0x408e  ldarga.s 4
0x4090  ldstr    aD_0// "D"
0x4095  call     instance string [mscorlib]System.Guid::ToString(string)
0x409a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x409f  pop
0x40a0  ldloc.3
0x40a1  ldloc.0
0x40a2  callvirt instance string [mscorlib]System.Object::ToString()
0x40a7  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x40ac  ldarg.0
0x40ad  ldloc.3
0x40ae  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x40b3  leave.s  loc_40BF
0x40b5  ldloc.3
0x40b6  brfalse.s loc_40BE
0x40b8  ldloc.3
0x40b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40be  endfinally
0x40bf  ret
```
