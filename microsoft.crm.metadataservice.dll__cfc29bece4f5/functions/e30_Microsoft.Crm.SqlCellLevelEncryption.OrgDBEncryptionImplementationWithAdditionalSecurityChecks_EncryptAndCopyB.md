# Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::EncryptAndCopyBackAllDataToMainTables

- ea: `0xe30`
- end: `0xf1c`
- name: `Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationWithAdditionalSecurityChecks::EncryptAndCopyBackAllDataToMainTables`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x260`

## callees

- `0xab0`
- `0xe30`
- `0x1090`
- `0x10a0`

## string_xrefs

- `0xeeb`: `D:\a\1\s\src\Core\ObjectModel\Metadata\MetadataService\SqlEncryption\OrgDBEncryptionImplementation.cs`
- `0xe7d`: `UPDATE {0}\n	SET {1} = ENCRYPTBYKEY(Key_GUID('[CrmSymmetricKey1]'), dd.Value, 1, CONVERT(varbinary(16), {2}))\n	FROM {0} t INNER JOIN #DecryptedData dd \n		ON t.{2} = dd.ObjectId AND dd.ObjectTypeCode = @ObjectTypeCode AND dd.ColumnNumber = @ColumnNumber\n`
- `0xee6`: `EncryptAndCopyBackAllDataToMainTables`

## pseudocode

```c

```

## disassembly

```asm
0xe30  ldarg.1
0xe31  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.IEncryptedColumnMetadata>::GetEnumerator()
0xe36  stloc.0
0xe37  br       loc_F04
0xe3c  ldloc.0
0xe3d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.IEncryptedColumnMetadata>::get_Current()
0xe42  dup
0xe43  castclass Microsoft.Crm.SqlCellLevelEncryption.OrganizationDatabaseEncryptedColumnMetadata
0xe48  stloc.1
0xe49  dup
0xe4a  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.IEncryptedColumnMetadata::get_TableName()
0xe4f  stloc.2
0xe50  ldloc.1
0xe51  callvirt instance int32 Microsoft.Crm.SqlCellLevelEncryption.OrganizationDatabaseEncryptedColumnMetadata::get_ObjecTypeCode()
0xe56  stloc.3
0xe57  dup
0xe58  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.IEncryptedColumnMetadata::get_EncryptedColumnName()
0xe5d  stloc.s  4
0xe5f  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.SqlCellLevelEncryption.IEncryptedColumnMetadata::get_PrimaryKeyColumnName()
0xe64  stloc.s  5
0xe66  ldloc.1
0xe67  callvirt instance int32 Microsoft.Crm.SqlCellLevelEncryption.OrganizationDatabaseEncryptedColumnMetadata::get_EncryptedColumnNumber()
0xe6c  stloc.s  6
0xe6e  ldarg.0
0xe6f  call     instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.SqlCellLevelEncryption.OrgDBEncryptionImplementationBase::CreateCommand()
0xe74  stloc.s  7
0xe76  ldloc.s  7
0xe78  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe7d  ldstr    aUpdate0Set1Enc// "UPDATE {0}\r\n\tSET {1} = ENCRYPTBYKEY("...
0xe82  ldc.i4.3
0xe83  newarr   [mscorlib]System.Object
0xe88  dup
0xe89  ldc.i4.0
0xe8a  ldloc.2
0xe8b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xe90  stelem.ref
0xe91  dup
0xe92  ldc.i4.1
0xe93  ldloc.s  4
0xe95  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xe9a  stelem.ref
0xe9b  dup
0xe9c  ldc.i4.2
0xe9d  ldloc.s  5
0xe9f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0xea4  stelem.ref
0xea5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xeaa  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xeaf  ldloc.s  7
0xeb1  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xeb6  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xebb  dup
0xebc  ldstr    aObjecttypecode// "@ObjectTypeCode"
0xec1  ldloc.3
0xec2  box      [mscorlib]System.Int32
0xec7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xecc  pop
0xecd  ldstr    aColumnnumber// "@ColumnNumber"
0xed2  ldloc.s  6
0xed4  box      [mscorlib]System.Int32
0xed9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xede  pop
0xedf  ldloc.s  7
0xee1  ldc.i4   0x202
0xee6  ldstr    aEncryptandcopy// "EncryptAndCopyBackAllDataToMainTables"
0xeeb  ldstr    aDA1SSrcCoreObj// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Me"...
0xef0  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xef5  pop
0xef6  leave.s  loc_F04
0xef8  ldloc.s  7
0xefa  brfalse.s loc_F03
0xefc  ldloc.s  7
0xefe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf03  endfinally
0xf04  ldloc.0
0xf05  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf0a  brtrue   loc_E3C
0xf0f  leave.s  loc_F1B
0xf11  ldloc.0
0xf12  brfalse.s loc_F1A
0xf14  ldloc.0
0xf15  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf1a  endfinally
0xf1b  ret
```
