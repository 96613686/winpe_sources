# Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::DecryptAndCopyAllDataToTempTable

- ea: `0xd40`
- end: `0xe2c`
- name: `Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::DecryptAndCopyAllDataToTempTable`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x260`

## callees

- `0xab0`
- `0xd40`
- `0x1040`
- `0x1090`
- `0x10a0`

## string_xrefs

- `0xdfb`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\SqlEncryption\OrgDBEncryptionImplementation.cs`
- `0xdf6`: `DecryptAndCopyAllDataToTempTable`

## pseudocode

```c

```

## disassembly

```asm
0xd40  ldarg.1
0xd41  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.IEncryptedColumnMetadata>::GetEnumerator()
0xd46  stloc.0
0xd47  br       loc_E14
0xd4c  ldloc.0
0xd4d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.IEncryptedColumnMetadata>::get_Current()
0xd52  dup
0xd53  castclass Microsoft.Crm.SqlCellLevelEncryption.OrganizationDatabaseEncryptedColumnMetadata
0xd58  stloc.1
0xd59  ldloc.1
0xd5a  callvirt instance string Microsoft.Crm.SqlCellLevelEncryption.OrganizationDatabaseEncryptedColumnMetadata::get_ViewName()
0xd5f  stloc.2
0xd60  ldloc.1
0xd61  callvirt instance int32 Microsoft.Crm.SqlCellLevelEncryption.OrganizationDatabaseEncryptedColumnMetadata::get_ObjecTypeCode()
0xd66  stloc.3
0xd67  dup
0xd68  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.IEncryptedColumnMetadata::get_EncryptedColumnName()
0xd6d  stloc.s  4
0xd6f  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.IEncryptedColumnMetadata::get_PrimaryKeyColumnName()
0xd74  stloc.s  5
0xd76  ldloc.1
0xd77  callvirt instance int32 Microsoft.Crm.SqlCellLevelEncryption.OrganizationDatabaseEncryptedColumnMetadata::get_EncryptedColumnNumber()
0xd7c  stloc.s  6
0xd7e  ldarg.0
0xd7f  call     instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationBase::CreateCommand()
0xd84  stloc.s  7
0xd86  ldloc.s  7
0xd88  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd8d  ldstr    aInsertIntoDecr// "INSERT INTO #DecryptedData(ObjectId, Ob"...
0xd92  ldc.i4.3
0xd93  newarr   [mscorlib]System.Object
0xd98  dup
0xd99  ldc.i4.0
0xd9a  ldloc.2
0xd9b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xda0  stelem.ref
0xda1  dup
0xda2  ldc.i4.1
0xda3  ldloc.s  4
0xda5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xdaa  stelem.ref
0xdab  dup
0xdac  ldc.i4.2
0xdad  ldloc.s  5
0xdaf  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xdb4  stelem.ref
0xdb5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdba  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xdbf  ldloc.s  7
0xdc1  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xdc6  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xdcb  dup
0xdcc  ldstr    aObjecttypecode// "@ObjectTypeCode"
0xdd1  ldloc.3
0xdd2  box      [mscorlib]System.Int32
0xdd7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xddc  pop
0xddd  ldstr    aColumnnumber// "@ColumnNumber"
0xde2  ldloc.s  6
0xde4  box      [mscorlib]System.Int32
0xde9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xdee  pop
0xdef  ldloc.s  7
0xdf1  ldc.i4   0x1E0
0xdf6  ldstr    aDecryptandcopy// "DecryptAndCopyAllDataToTempTable"
0xdfb  ldstr    aDA1SSrcCoreObj// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0xe00  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xe05  pop
0xe06  leave.s  loc_E14
0xe08  ldloc.s  7
0xe0a  brfalse.s loc_E13
0xe0c  ldloc.s  7
0xe0e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe13  endfinally
0xe14  ldloc.0
0xe15  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe1a  brtrue   loc_D4C
0xe1f  leave.s  loc_E2B
0xe21  ldloc.0
0xe22  brfalse.s loc_E2A
0xe24  ldloc.0
0xe25  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe2a  endfinally
0xe2b  ret
```
