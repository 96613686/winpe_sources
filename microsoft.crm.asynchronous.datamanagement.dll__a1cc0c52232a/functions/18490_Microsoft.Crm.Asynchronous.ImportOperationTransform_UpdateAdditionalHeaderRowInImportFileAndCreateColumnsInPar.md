# Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateAdditionalHeaderRowInImportFileAndCreateColumnsInParsedTable

- ea: `0x18490`
- end: `0x18682`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateAdditionalHeaderRowInImportFileAndCreateColumnsInParsedTable`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17670`

## callees

- `0x3b80`
- `0x3c60`
- `0x4420`
- `0x5ed0`
- `0x5fc0`
- `0x61f0`
- `0x18490`

## string_xrefs

- `0x1860e`: `UPDATE ImportFileBase SET AdditionalHeaderRow=@headerRow WHERE ImportFileId=@importFileId`

## pseudocode

```c

```

## disassembly

```asm
0x18490  ldarg.2
0x18491  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x18496  ldc.i4.0
0x18497  bgt.s    loc_1849A
0x18499  ret
0x1849a  ldarg.1
0x1849b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x184a0  ldstr    aAdditionalhead// "additionalheaderrow"
0x184a5  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x184aa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x184af  brtrue.s loc_184B2
0x184b1  ret
0x184b2  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x184b7  stloc.0
0x184b8  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x184bd  stloc.1
0x184be  ldarg.1
0x184bf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x184c4  ldstr    aParsedtablecol// "parsedtablecolumnprefix"
0x184c9  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x184ce  stloc.2
0x184cf  ldloc.1
0x184d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x184d5  ldstr    aAlterTableDbo0_0// "ALTER TABLE dbo.{0} ADD "
0x184da  ldc.i4.1
0x184db  newarr   [mscorlib]System.Object
0x184e0  dup
0x184e1  ldc.i4.0
0x184e2  ldarg.1
0x184e3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x184e8  ldstr    aParsedtablenam_0// "parsedtablename"
0x184ed  call     string Microsoft.Crm.Asynchronous.DataManagementHelper::GetStringFromDynamicEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity de, string propertyName)
0x184f2  stelem.ref
0x184f3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x184f8  pop
0x184f9  ldc.i4.0
0x184fa  stloc.3
0x184fb  br       loc_1859E
0x18500  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18505  ldstr    a01_0// "{0}{1}"
0x1850a  ldc.i4.2
0x1850b  newarr   [mscorlib]System.Object
0x18510  dup
0x18511  ldc.i4.0
0x18512  ldloc.2
0x18513  stelem.ref
0x18514  dup
0x18515  ldc.i4.1
0x18516  ldarg.1
0x18517  callvirt instance string[] Microsoft.Crm.Asynchronous.ImportFileHelperData::get_HeaderColumns()
0x1851c  ldlen
0x1851d  conv.i4
0x1851e  ldloc.3
0x1851f  add
0x18520  ldc.i4.1
0x18521  add
0x18522  box      [mscorlib]System.Int32
0x18527  stelem.ref
0x18528  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1852d  stloc.s  4
0x1852f  ldloc.0
0x18530  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18535  ldstr    a0_2// "{0},"
0x1853a  ldc.i4.1
0x1853b  newarr   [mscorlib]System.Object
0x18540  dup
0x18541  ldc.i4.0
0x18542  ldarg.2
0x18543  ldloc.3
0x18544  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x18549  stelem.ref
0x1854a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1854f  pop
0x18550  ldloc.1
0x18551  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18556  ldstr    a0Nvarchar1_0// "{0} nvarchar({1}),"
0x1855b  ldc.i4.2
0x1855c  newarr   [mscorlib]System.Object
0x18561  dup
0x18562  ldc.i4.0
0x18563  ldloc.s  4
0x18565  stelem.ref
0x18566  dup
0x18567  ldc.i4.1
0x18568  ldc.i4   0x1F4
0x1856d  box      [mscorlib]System.Int32
0x18572  stelem.ref
0x18573  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x18578  pop
0x18579  ldarg.1
0x1857a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ParsedTableColumnToColumnLengthDictionary()
0x1857f  ldloc.s  4
0x18581  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::ContainsKey(var<u1>)
0x18586  brtrue.s loc_1859A
0x18588  ldarg.1
0x18589  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ParsedTableColumnToColumnLengthDictionary()
0x1858e  ldloc.s  4
0x18590  ldc.i4   0x1F4
0x18595  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1859a  ldloc.3
0x1859b  ldc.i4.1
0x1859c  add
0x1859d  stloc.3
0x1859e  ldloc.3
0x1859f  ldarg.2
0x185a0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x185a5  blt      loc_18500
0x185aa  ldloc.0
0x185ab  ldloc.0
0x185ac  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x185b1  ldc.i4.1
0x185b2  sub
0x185b3  ldc.i4.1
0x185b4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0x185b9  pop
0x185ba  ldloc.1
0x185bb  ldloc.1
0x185bc  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x185c1  ldc.i4.1
0x185c2  sub
0x185c3  ldc.i4.1
0x185c4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Remove(int32, int32)
0x185c9  pop
0x185ca  ldarg.0
0x185cb  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x185d0  ldarg.0
0x185d1  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0x185d6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x185db  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.ImportDataAccess::CreateDatabaseConnection(valuetype [mscorlib]System.Guid organizationId)
0x185e0  stloc.s  5
0x185e2  ldloc.s  5
0x185e4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x185e9  ldloc.s  5
0x185eb  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x185f0  stloc.s  6
0x185f2  ldloc.s  6
0x185f4  ldloc.1
0x185f5  callvirt instance string [mscorlib]System.Object::ToString()
0x185fa  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x185ff  ldarg.0
0x18600  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x18605  ldloc.s  6
0x18607  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSQLCommandWithExtendedTimeout(class [System.Data]System.Data.IDbCommand command)
0x1860c  ldloc.s  6
0x1860e  ldstr    aUpdateImportfi_9// "UPDATE ImportFileBase SET AdditionalHea"...
0x18613  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x18618  ldloc.s  6
0x1861a  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1861f  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x18624  dup
0x18625  ldstr    aHeaderrow_0// "@headerRow"
0x1862a  ldloc.0
0x1862b  callvirt instance string [mscorlib]System.Object::ToString()
0x18630  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x18635  pop
0x18636  ldstr    aImportfileid_0// "@importFileId"
0x1863b  ldarg.1
0x1863c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::get_ImportFile()
0x18641  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x18646  stloc.s  7
0x18648  ldloca.s 7
0x1864a  ldstr    aD_0// "D"
0x1864f  call     instance string [mscorlib]System.Guid::ToString(string)
0x18654  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x18659  pop
0x1865a  ldarg.0
0x1865b  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0x18660  ldloc.s  6
0x18662  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::ExecuteSQLCommandWithExtendedTimeout(class [System.Data]System.Data.IDbCommand command)
0x18667  leave.s  loc_18681
0x18669  ldloc.s  6
0x1866b  brfalse.s loc_18674
0x1866d  ldloc.s  6
0x1866f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18674  endfinally
0x18675  ldloc.s  5
0x18677  brfalse.s loc_18680
0x18679  ldloc.s  5
0x1867b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18680  endfinally
0x18681  ret
```
