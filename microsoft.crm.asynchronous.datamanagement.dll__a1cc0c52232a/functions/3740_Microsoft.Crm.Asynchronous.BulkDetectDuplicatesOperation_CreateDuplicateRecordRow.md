# Microsoft.Crm.Asynchronous.BulkDetectDuplicatesOperation::CreateDuplicateRecordRow

- ea: `0x3740`
- end: `0x37a9`
- name: `Microsoft.Crm.Asynchronous.BulkDetectDuplicatesOperation::CreateDuplicateRecordRow`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3550`

## callees

- `0x1fc30`

## string_xrefs

- `0x3741`: `INSERT INTO DuplicateRecordBase(DuplicateId, \n																	BaseRecordId, \n																	AsyncOperationId, \n																	CreatedOn, \n																	BaseRecordIdTypeCode) \n				VALUES(NEWID(), @recordId, @asyncOperationId, GETDATE(), @objectTypeCode)`

## pseudocode

```c

```

## disassembly

```asm
0x3740  ldarg.1
0x3741  ldstr    aInsertIntoDupl// "INSERT INTO DuplicateRecordBase(Duplica"...
0x3746  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x374b  ldarg.1
0x374c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x3751  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3756  dup
0x3757  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x375c  dup
0x375d  ldstr    aRecordid// "@recordId"
0x3762  ldarg.2
0x3763  box      [mscorlib]System.Guid
0x3768  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x376d  pop
0x376e  dup
0x376f  ldstr    aAsyncoperation// "@asyncOperationId"
0x3774  ldarg.0
0x3775  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.BulkDetectDuplicatesOperation::_asyncEvent
0x377a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x377f  box      [mscorlib]System.Guid
0x3784  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x3789  pop
0x378a  ldstr    aObjecttypecode// "@objectTypeCode"
0x378f  ldarg.3
0x3790  box      [mscorlib]System.Int32
0x3795  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x379a  pop
0x379b  ldarg.0
0x379c  ldfld    class BulkDetectDuplicatesDataAccess Microsoft.Crm.Asynchronous.BulkDetectDuplicatesOperation::_dataAccess
0x37a1  ldarg.1
0x37a2  callvirt instance object BulkDetectDuplicatesDataAccess::ExecuteCommand(class [System.Data]System.Data.IDbCommand command)
0x37a7  pop
0x37a8  ret
```
