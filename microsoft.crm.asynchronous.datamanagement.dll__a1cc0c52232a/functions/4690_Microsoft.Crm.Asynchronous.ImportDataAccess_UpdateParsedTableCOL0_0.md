# Microsoft.Crm.Asynchronous.ImportDataAccess::UpdateParsedTableCOL0_0

- ea: `0x4690`
- end: `0x4751`
- name: `Microsoft.Crm.Asynchronous.ImportDataAccess::UpdateParsedTableCOL0_0`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4670`

## callees

- `0x4540`
- `0x4690`

## string_xrefs

- `0x4695`: `UPDATE {0} SET IsTransformed = {1}, {2}0 = @recordId, IsExistingRecord = @isExistingRecord WHERE ImportDataId = @importDataId;\n																			UPDATE ImportDataBase SET RecordId = @recordId WHERE ImportDataId = @importDataId`

## pseudocode

```c

```

## disassembly

```asm
0x4690  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4695  ldstr    aUpdate0SetIstr// "UPDATE {0} SET IsTransformed = {1}, {2}"...
0x469a  ldc.i4.3
0x469b  newarr   [mscorlib]System.Object
0x46a0  dup
0x46a1  ldc.i4.0
0x46a2  ldarg.1
0x46a3  stelem.ref
0x46a4  dup
0x46a5  ldc.i4.1
0x46a6  ldarg.s  6
0x46a8  box      [mscorlib]System.Int32
0x46ad  stelem.ref
0x46ae  dup
0x46af  ldc.i4.2
0x46b0  ldarg.2
0x46b1  stelem.ref
0x46b2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x46b7  callvirt instance string [mscorlib]System.Object::ToString()
0x46bc  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x46c1  stloc.0
0x46c2  ldloc.0
0x46c3  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x46c8  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x46cd  stloc.1
0x46ce  ldloc.1
0x46cf  ldstr    aRecordid// "@recordId"
0x46d4  ldarga.s 3
0x46d6  ldstr    aD_0// "D"
0x46db  call     instance string [mscorlib]System.Guid::ToString(string)
0x46e0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x46e5  pop
0x46e6  ldloc.1
0x46e7  ldstr    aImportdataid_0// "@importDataId"
0x46ec  ldarga.s 4
0x46ee  ldstr    aD_0// "D"
0x46f3  call     instance string [mscorlib]System.Guid::ToString(string)
0x46f8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x46fd  pop
0x46fe  ldarg.s  5
0x4700  stloc.2
0x4701  ldc.i4.1
0x4702  stloc.3
0x4703  ldloca.s 2
0x4705  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x470a  ldloc.3
0x470b  beq.s    loc_4710
0x470d  ldc.i4.0
0x470e  br.s     loc_4717
0x4710  ldloca.s 2
0x4712  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4717  brfalse.s loc_472C
0x4719  ldloc.1
0x471a  ldstr    aIsexistingreco// "@isExistingRecord"
0x471f  ldstr    a1// "1"
0x4724  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4729  pop
0x472a  br.s     loc_473D
0x472c  ldloc.1
0x472d  ldstr    aIsexistingreco// "@isExistingRecord"
0x4732  ldstr    a0_0// "0"
0x4737  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x473c  pop
0x473d  ldarg.0
0x473e  ldloc.0
0x473f  call     instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSqlCommandWithNoExpectedRecords(class [System.Data]System.Data.IDbCommand sqlCommand)
0x4744  leave.s  loc_4750
0x4746  ldloc.0
0x4747  brfalse.s loc_474F
0x4749  ldloc.0
0x474a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x474f  endfinally
0x4750  ret
```
