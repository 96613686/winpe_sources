# Microsoft.Crm.Asynchronous.EmailConnector.Utility::FetchFolderMappingsFromCrm

- ea: `0x40fc0`
- end: `0x41180`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.Utility::FetchFolderMappingsFromCrm`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x401e0`

## callees

- `0x366d0`
- `0x366e0`
- `0x366f0`
- `0x36710`
- `0x36730`
- `0x36750`
- `0x36770`
- `0x36790`
- `0x367b0`
- `0x367c0`
- `0x40fc0`
- `0x411e0`

## string_xrefs

- `0x40fe7`: `SELECT MailboxTrackingFolderId, \n													MailboxId,\n													ExchangeFolderId,\n													ExchangeFolderName,\n													RegardingObjectId,\n													RegardingObjectTypeCode,\n													RegardingObjectIdName,\n													FolderOnboardingStatus\n											FROM MailboxTrackingFolderBase with (READPAST, READCOMMITTEDLOCK) \n											where MailboxId = @mailboxId AND ModifiedOn <= @dateTimeNow `
- `0x4102a`: `d:\dbs\sh\dccm2\1101_190851\cmd\55\src\Core\ObjectModel\Async\Handlers\EmailConnector\ActivityProviders\Incoming\Utility.cs`

## pseudocode

```c

```

## disassembly

```asm
0x40fc0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.FolderBasedTrackingSyncFolder>::.ctor()
0x40fc5  stloc.0
0x40fc6  ldarg.0
0x40fc7  call     bool Microsoft.Crm.Asynchronous.EmailConnector.Utility::IsDbDeployedGreaterThanOrEqualToCarina(valuetype [mscorlib]System.Guid organizationId)
0x40fcc  brtrue.s loc_40FD0
0x40fce  ldloc.0
0x40fcf  ret
0x40fd0  ldarg.0
0x40fd1  ldc.i4.0
0x40fd2  ldc.i4.0
0x40fd3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x40fd8  stloc.1
0x40fd9  ldloc.1
0x40fda  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x40fdf  ldloc.1
0x40fe0  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x40fe5  stloc.2
0x40fe6  ldloc.2
0x40fe7  ldstr    aSelectMailboxt// "SELECT MailboxTrackingFolderId, \r\n\t"...
0x40fec  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x40ff1  ldloc.2
0x40ff2  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x40ff7  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x40ffc  dup
0x40ffd  ldstr    aMailboxid_1// "@mailboxId"
0x41002  ldarg.1
0x41003  box      [mscorlib]System.Guid
0x41008  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4100d  pop
0x4100e  ldstr    aDatetimenow// "@dateTimeNow"
0x41013  ldarg.2
0x41014  box      [mscorlib]System.DateTime
0x41019  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4101e  pop
0x4101f  ldloc.2
0x41020  ldc.i4   0xCB
0x41025  ldstr    aFetchfoldermap// "FetchFolderMappingsFromCrm"
0x4102a  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x4102f  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x41034  stloc.3
0x41035  br       loc_41153
0x4103a  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.FolderBasedTrackingSyncFolder::.ctor()
0x4103f  stloc.s  4
0x41041  ldloc.s  4
0x41043  ldloc.3
0x41044  ldstr    aMailboxtrackin_1// "MailboxTrackingFolderId"
0x41049  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x4104e  unbox.any [mscorlib]System.Guid
0x41053  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.FolderBasedTrackingSyncFolder::set_Id(valuetype [mscorlib]System.Guid value)
0x41058  ldloc.s  4
0x4105a  ldloc.3
0x4105b  ldstr    aMailboxid_0// "MailboxId"
0x41060  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x41065  unbox.any [mscorlib]System.Guid
0x4106a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.FolderBasedTrackingSyncFolder::set_MailboxId(valuetype [mscorlib]System.Guid value)
0x4106f  ldloc.s  4
0x41071  ldloc.3
0x41072  ldstr    aExchangefolder_1// "ExchangeFolderId"
0x41077  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x4107c  callvirt instance string [mscorlib]System.Object::ToString()
0x41081  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.FolderBasedTrackingSyncFolder::set_ExchangeFolderId(string value)
0x41086  ldloc.s  4
0x41088  ldloc.3
0x41089  ldstr    aExchangefolder_2// "ExchangeFolderName"
0x4108e  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x41093  callvirt instance string [mscorlib]System.Object::ToString()
0x41098  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.FolderBasedTrackingSyncFolder::set_ExchangeFolderName(string value)
0x4109d  ldloc.s  4
0x4109f  ldloc.3
0x410a0  ldstr    aRegardingobjec_5// "RegardingObjectId"
0x410a5  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x410aa  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x410af  beq.s    loc_410C3
0x410b1  ldloc.3
0x410b2  ldstr    aRegardingobjec_5// "RegardingObjectId"
0x410b7  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x410bc  unbox.any [mscorlib]System.Guid
0x410c1  br.s     loc_410C8
0x410c3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x410c8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.FolderBasedTrackingSyncFolder::set_RegardingObjectId(valuetype [mscorlib]System.Guid value)
0x410cd  ldloc.s  4
0x410cf  ldloc.3
0x410d0  ldstr    aRegardingobjec_6// "RegardingObjectTypeCode"
0x410d5  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x410da  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x410df  beq.s    loc_410F3
0x410e1  ldloc.3
0x410e2  ldstr    aRegardingobjec_6// "RegardingObjectTypeCode"
0x410e7  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x410ec  callvirt instance string [mscorlib]System.Object::ToString()
0x410f1  br.s     loc_410F8
0x410f3  ldsfld   string [mscorlib]System.String::Empty
0x410f8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.FolderBasedTrackingSyncFolder::set_RegardingObjectTypeCode(string value)
0x410fd  ldloc.s  4
0x410ff  ldloc.3
0x41100  ldstr    aRegardingobjec_7// "RegardingObjectIdName"
0x41105  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x4110a  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x4110f  beq.s    loc_41123
0x41111  ldloc.3
0x41112  ldstr    aRegardingobjec_7// "RegardingObjectIdName"
0x41117  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x4111c  callvirt instance string [mscorlib]System.Object::ToString()
0x41121  br.s     loc_41128
0x41123  ldsfld   string [mscorlib]System.String::Empty
0x41128  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.FolderBasedTrackingSyncFolder::set_RegardingObjectName(string value)
0x4112d  ldloc.s  4
0x4112f  ldloc.3
0x41130  ldstr    aFolderonboardi// "FolderOnboardingStatus"
0x41135  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x4113a  unbox.any [mscorlib]System.Int32
0x4113f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.FolderBasedTrackingSyncFolder::set_FolderOnboardingStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.FolderOnboardingStatus value)
0x41144  ldloc.0
0x41145  ldloc.s  4
0x41147  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.FolderBasedTrackingSyncFolder::get_ExchangeFolderId()
0x4114c  ldloc.s  4
0x4114e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.FolderBasedTrackingSyncFolder>::Add(var<u1>, !!T0)
0x41153  ldloc.3
0x41154  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x41159  brtrue   loc_4103A
0x4115e  leave.s  loc_4117E
0x41160  ldloc.3
0x41161  brfalse.s loc_41169
0x41163  ldloc.3
0x41164  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41169  endfinally
0x4116a  ldloc.2
0x4116b  brfalse.s loc_41173
0x4116d  ldloc.2
0x4116e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41173  endfinally
0x41174  ldloc.1
0x41175  brfalse.s loc_4117D
0x41177  ldloc.1
0x41178  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4117d  endfinally
0x4117e  ldloc.0
0x4117f  ret
```
