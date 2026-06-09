# Microsoft.Crm.CrmKeyArchiveManager::CleanupKeys

- ea: `0x37bc0`
- end: `0x37dc2`
- name: `Microsoft.Crm.CrmKeyArchiveManager::CleanupKeys`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x37ba0`

## callees

- `0xd2f0`
- `0xd620`
- `0xd7c0`
- `0xdab0`
- `0x17cc0`
- `0x1f4b0`
- `0x37bc0`
- `0x396a0`
- `0x39910`
- `0x39a90`
- `0x39ab0`
- `0x3d640`
- `0x4a830`

## string_xrefs

- `0x37cc1`: `@CreatedOn`
- `0x37d48`: `@CreatedOn`
- `0x37c18`: `CrmKeyArchiveManager : Cleaning up any expired keys created on or before : {0}. {1}`
- `0x37c78`: `\nDELETE FROM CrmKeyProperties\nWHERE	Id in \n		(SELECT Id FROM CrmKey WHERE\n			KeyType = @KeyType AND \n			ScaleGroupId = @ScaleGroupId AND \n			CreatedOn < @CreatedOn AND\n			Id <> @ActiveKeyId)`
- `0x37cf2`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKeyArchiveManager.cs`
- `0x37d79`: `D:\a\1\s\src\Platform\Core\Security\Cryptography\CrmKeyArchiveManager.cs`
- `0x37cff`: `\nDELETE FROM CrmKey \nWHERE	KeyType = @KeyType AND \n		ScaleGroupId = @ScaleGroupId AND \n		CreatedOn < @CreatedOn AND\n			Id <> @ActiveKeyId`

## pseudocode

```c

```

## disassembly

```asm
0x37bc0  ldarg.0
0x37bc1  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.CrmKeyType> Microsoft.Crm.CrmKeyArchiveManager::_keyTypes
0x37bc6  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.Crm.CrmKeyType>::GetEnumerator()
0x37bcb  stloc.0
0x37bcc  br       loc_37DA5
0x37bd1  ldloca.s 0
0x37bd3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype Microsoft.Crm.CrmKeyType>::get_Current()
0x37bd8  stloc.1
0x37bd9  ldloc.1
0x37bda  call     class Microsoft.Crm.CrmKeySetting Microsoft.Crm.CrmKeySetting::LoadKeySetting(valuetype Microsoft.Crm.CrmKeyType keyType)
0x37bdf  stloc.2
0x37be0  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x37be5  stloc.3
0x37be6  ldloc.2
0x37be7  callvirt instance int32 Microsoft.Crm.CrmKeySetting::get_KeyTimeToLive()
0x37bec  ldc.i4.0
0x37bed  blt.s    loc_37C11
0x37bef  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x37bf4  stloc.s  4
0x37bf6  ldloca.s 4
0x37bf8  ldloc.2
0x37bf9  callvirt instance int32 Microsoft.Crm.CrmKeySetting::get_ArchiveLength()
0x37bfe  ldloc.2
0x37bff  callvirt instance int32 Microsoft.Crm.CrmKeySetting::get_KeyTimeToLive()
0x37c04  ldc.i4.0
0x37c05  ldc.i4.0
0x37c06  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32, int32)
0x37c0b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.TimeSpan)
0x37c10  stloc.3
0x37c11  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x37c16  ldc.i4.s 0x14
0x37c18  ldstr    aCrmkeyarchivem// "CrmKeyArchiveManager : Cleaning up any "...
0x37c1d  ldc.i4.2
0x37c1e  newarr   [mscorlib]System.Object
0x37c23  dup
0x37c24  ldc.i4.0
0x37c25  ldloc.3
0x37c26  box      [mscorlib]System.DateTime
0x37c2b  stelem.ref
0x37c2c  dup
0x37c2d  ldc.i4.1
0x37c2e  ldloc.2
0x37c2f  stelem.ref
0x37c30  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x37c35  ldarg.0
0x37c36  call     instance class Microsoft.Crm.ICrmEventLog Microsoft.Crm.ThreadControllable::get_EventLog()
0x37c3b  ldc.i4.4
0x37c3c  ldc.i4   0x40004A0A
0x37c41  conv.i8
0x37c42  ldc.i4.2
0x37c43  newarr   [mscorlib]System.Object
0x37c48  dup
0x37c49  ldc.i4.0
0x37c4a  ldloc.1
0x37c4b  box      Microsoft.Crm.CrmKeyType
0x37c50  stelem.ref
0x37c51  dup
0x37c52  ldc.i4.1
0x37c53  ldloc.3
0x37c54  box      [mscorlib]System.DateTime
0x37c59  stelem.ref
0x37c5a  callvirt instance void Microsoft.Crm.ICrmEventLog::WriteEntry(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] values)
0x37c5f  call     class Microsoft.Crm.CrmDbConnection Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetGeoConfigDBConnection()
0x37c64  stloc.s  5
0x37c66  ldloc.s  5
0x37c68  callvirt instance void Microsoft.Crm.CrmDbConnection::Open()
0x37c6d  ldloc.s  5
0x37c6f  callvirt instance class [System.Data]System.Data.IDbTransaction Microsoft.Crm.CrmDbConnection::BeginTransaction()
0x37c74  stloc.s  6
0x37c76  ldloc.s  5
0x37c78  ldstr    aDeleteFromCrmk// "\r\nDELETE FROM CrmKeyProperties\r\nWHE"...
0x37c7d  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand(string commandText)
0x37c82  dup
0x37c83  ldloc.s  6
0x37c85  callvirt instance void [System.Data]System.Data.IDbCommand::set_Transaction(class [System.Data]System.Data.IDbTransaction)
0x37c8a  dup
0x37c8b  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x37c90  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x37c95  dup
0x37c96  ldstr    aKeytype_0// "@KeyType"
0x37c9b  ldloca.s 1
0x37c9d  constrained. Microsoft.Crm.CrmKeyType
0x37ca3  callvirt instance string [mscorlib]System.Object::ToString()
0x37ca8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x37cad  pop
0x37cae  dup
0x37caf  ldstr    aScalegroupid_1// "@ScaleGroupId"
0x37cb4  ldarg.1
0x37cb5  box      [mscorlib]System.Guid
0x37cba  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x37cbf  pop
0x37cc0  dup
0x37cc1  ldstr    aCreatedon_0// "@CreatedOn"
0x37cc6  ldloc.3
0x37cc7  box      [mscorlib]System.DateTime
0x37ccc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x37cd1  pop
0x37cd2  ldstr    aActivekeyid// "@ActiveKeyId"
0x37cd7  ldloc.2
0x37cd8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeySetting::get_ActiveKeyId()
0x37cdd  box      [mscorlib]System.Guid
0x37ce2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x37ce7  pop
0x37ce8  ldc.i4   0x9F
0x37ced  ldstr    aCleanupkeys// "CleanupKeys"
0x37cf2  ldstr    aDA1SSrcPlatfor_17// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x37cf7  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x37cfc  pop
0x37cfd  ldloc.s  5
0x37cff  ldstr    aDeleteFromCrmk_0// "\r\nDELETE FROM CrmKey \r\nWHERE\tKeyTy"...
0x37d04  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.CrmDbConnection::CreateCommand(string commandText)
0x37d09  dup
0x37d0a  ldloc.s  6
0x37d0c  callvirt instance void [System.Data]System.Data.IDbCommand::set_Transaction(class [System.Data]System.Data.IDbTransaction)
0x37d11  dup
0x37d12  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x37d17  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x37d1c  dup
0x37d1d  ldstr    aKeytype_0// "@KeyType"
0x37d22  ldloca.s 1
0x37d24  constrained. Microsoft.Crm.CrmKeyType
0x37d2a  callvirt instance string [mscorlib]System.Object::ToString()
0x37d2f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x37d34  pop
0x37d35  dup
0x37d36  ldstr    aScalegroupid_1// "@ScaleGroupId"
0x37d3b  ldarg.1
0x37d3c  box      [mscorlib]System.Guid
0x37d41  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x37d46  pop
0x37d47  dup
0x37d48  ldstr    aCreatedon_0// "@CreatedOn"
0x37d4d  ldloc.3
0x37d4e  box      [mscorlib]System.DateTime
0x37d53  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x37d58  pop
0x37d59  ldstr    aActivekeyid// "@ActiveKeyId"
0x37d5e  ldloc.2
0x37d5f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmKeySetting::get_ActiveKeyId()
0x37d64  box      [mscorlib]System.Guid
0x37d69  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x37d6e  pop
0x37d6f  ldc.i4   0xAB
0x37d74  ldstr    aCleanupkeys// "CleanupKeys"
0x37d79  ldstr    aDA1SSrcPlatfor_17// "D:\\a\\1\\s\\src\\Platform\\Core\\Secur"...
0x37d7e  call     int32 Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x37d83  pop
0x37d84  ldloc.s  6
0x37d86  callvirt instance void [System.Data]System.Data.IDbTransaction::Commit()
0x37d8b  leave.s  loc_37DA5
0x37d8d  ldloc.s  6
0x37d8f  brfalse.s loc_37D98
0x37d91  ldloc.s  6
0x37d93  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37d98  endfinally
0x37d99  ldloc.s  5
0x37d9b  brfalse.s loc_37DA4
0x37d9d  ldloc.s  5
0x37d9f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37da4  endfinally
0x37da5  ldloca.s 0
0x37da7  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype Microsoft.Crm.CrmKeyType>::MoveNext()
0x37dac  brtrue   loc_37BD1
0x37db1  leave.s  loc_37DC1
0x37db3  ldloca.s 0
0x37db5  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype Microsoft.Crm.CrmKeyType>
0x37dbb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37dc0  endfinally
0x37dc1  ret
```
