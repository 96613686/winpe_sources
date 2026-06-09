# ResourceBookingsWithChangedUserToDeleteQuerySQL::RetrieveNextPage

- ea: `0x14f20`
- end: `0x1519e`
- name: `ResourceBookingsWithChangedUserToDeleteQuerySQL::RetrieveNextPage`
- size: `638`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x8ab0`
- `0x14190`
- `0x14f20`

## string_xrefs

- `0x14fb2`: `AND BookableResourceBookingExchangeSyncIdMapping.IsDeletedInExchange = 0`
- `0x15168`: `ResourceBookingsWithChangedUserToDeleteQuerySQL`

## pseudocode

```c

```

## disassembly

```asm
0x14f20  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x14f25  stloc.0
0x14f26  ldarg.1
0x14f27  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x14f2c  stloc.1
0x14f2d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x14f32  stloc.2
0x14f33  ldloc.1
0x14f34  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x14f39  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x14f3e  stloc.3
0x14f3f  ldloc.3
0x14f40  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x14f45  ldloc.2
0x14f46  ldstr    aSelectBookable_1// "SELECT BookableResourceBookingExchangeS"...
0x14f4b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14f50  pop
0x14f51  ldloc.2
0x14f52  ldstr    aBookableresour_6// "BookableResourceBookingExchangeSyncIdMa"...
0x14f57  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14f5c  pop
0x14f5d  ldloc.2
0x14f5e  ldstr    aBookableresour_9// "BookableResourceBookingExchangeSyncIdMa"...
0x14f63  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14f68  pop
0x14f69  ldloc.2
0x14f6a  ldstr    aBookableresour_10// "BookableResourceBookingExchangeSyncIdMa"...
0x14f6f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14f74  pop
0x14f75  ldloc.2
0x14f76  ldstr    aFromBookablere_0// "FROM BookableResourceBookingExchangeSyn"...
0x14f7b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14f80  pop
0x14f81  ldloc.2
0x14f82  ldstr    aJoinBookablere_1// "JOIN BookableResourceBooking"
0x14f87  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14f8c  pop
0x14f8d  ldloc.2
0x14f8e  ldstr    aOnBookablereso_1// "ON BookableResourceBooking.BookableReso"...
0x14f93  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14f98  pop
0x14f99  ldloc.2
0x14f9a  ldstr    aJoinBookablere_2// "JOIN BookableResource ON BookableResour"...
0x14f9f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14fa4  pop
0x14fa5  ldloc.2
0x14fa6  ldstr    aWhereBookabler_8// "WHERE BookableResourceBookingExchangeSy"...
0x14fab  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14fb0  pop
0x14fb1  ldloc.2
0x14fb2  ldstr    aAndBookableres_12// "AND BookableResourceBookingExchangeSync"...
0x14fb7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14fbc  pop
0x14fbd  ldarg.0
0x14fbe  call     instance bool PagedEntitySQLQuery::get_IsPagingEnabled()
0x14fc3  brfalse.s loc_1501D
0x14fc5  ldloc.2
0x14fc6  ldstr    aAndBookableres_10// "AND ((BookableResourceBookingExchangeSy"...
0x14fcb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14fd0  pop
0x14fd1  ldloc.2
0x14fd2  ldstr    aAndBookableres_11// "AND BookableResourceBookingExchangeSync"...
0x14fd7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14fdc  pop
0x14fdd  ldloc.2
0x14fde  ldstr    aOrBookablereso_2// "OR BookableResourceBookingExchangeSyncI"...
0x14fe3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14fe8  pop
0x14fe9  ldloc.3
0x14fea  ldstr    aPreviouspageid// "@previousPageId"
0x14fef  ldarg.0
0x14ff0  ldflda   valuetype [mscorlib]System.Guid ResourceBookingsWithChangedUserToDeleteQuerySQL::previousPageId
0x14ff5  constrained. [mscorlib]System.Guid
0x14ffb  callvirt instance string [mscorlib]System.Object::ToString()
0x15000  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x15005  pop
0x15006  ldloc.3
0x15007  ldstr    aPreviouspageve// "@previousPageVersionNumber"
0x1500c  ldarg.0
0x1500d  ldfld    int64 ResourceBookingsWithChangedUserToDeleteQuerySQL::previousPageVersionNumber
0x15012  box      [mscorlib]System.Int64
0x15017  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1501c  pop
0x1501d  ldloc.2
0x1501e  ldstr    aOrderByBookabl_0// "ORDER BY BookableResourceBookingExchang"...
0x15023  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x15028  pop
0x15029  ldarg.0
0x1502a  call     instance bool PagedEntitySQLQuery::get_IsPagingEnabled()
0x1502f  brfalse.s loc_15066
0x15031  ldloc.2
0x15032  ldstr    aOffsetOffsetRo// "OFFSET @offset ROWS FETCH NEXT @pageSiz"...
0x15037  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1503c  pop
0x1503d  ldloc.3
0x1503e  ldstr    aOffset// "@offset"
0x15043  ldc.i4.0
0x15044  box      [mscorlib]System.Int32
0x15049  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1504e  pop
0x1504f  ldloc.3
0x15050  ldstr    aPagesize// "@pageSize"
0x15055  ldarg.0
0x15056  ldfld    int32 PagedEntitySQLQuery::maxPageSize
0x1505b  box      [mscorlib]System.Int32
0x15060  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x15065  pop
0x15066  ldloc.1
0x15067  ldloc.2
0x15068  callvirt instance string [mscorlib]System.Object::ToString()
0x1506d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x15072  ldloc.1
0x15073  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x15078  stloc.s  4
0x1507a  br       loc_15144
0x1507f  ldloc.s  4
0x15081  ldstr    aUserid_0// "UserId"
0x15086  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1508b  unbox.any [mscorlib]System.Guid
0x15090  stloc.s  5
0x15092  ldloc.s  4
0x15094  ldstr    aSyncversionnum_1// "SyncVersionNumber"
0x15099  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1509e  unbox.any [mscorlib]System.Int64
0x150a3  stloc.s  6
0x150a5  ldarg.0
0x150a6  call     instance bool PagedEntitySQLQuery::get_IsPagingEnabled()
0x150ab  brfalse.s loc_150BD
0x150ad  ldarg.0
0x150ae  ldloc.s  5
0x150b0  stfld    valuetype [mscorlib]System.Guid ResourceBookingsWithChangedUserToDeleteQuerySQL::previousPageId
0x150b5  ldarg.0
0x150b6  ldloc.s  6
0x150b8  stfld    int64 ResourceBookingsWithChangedUserToDeleteQuerySQL::previousPageVersionNumber
0x150bd  ldstr    aBookableresour_11// "bookableresourcebookingexchangesyncidma"...
0x150c2  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x150c7  stloc.s  7
0x150c9  ldloc.s  7
0x150cb  ldstr    aBookableresour// "bookableresourcebookingexchangesyncidma"...
0x150d0  ldloc.s  4
0x150d2  ldstr    aBookableresour_8// "BookableResourceBookingExchangeSyncIdMa"...
0x150d7  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x150dc  unbox.any [mscorlib]System.Guid
0x150e1  box      [mscorlib]System.Guid
0x150e6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x150eb  ldloc.s  7
0x150ed  ldstr    aUserid// "userid"
0x150f2  ldstr    aSystemuser// "systemuser"
0x150f7  ldloc.s  5
0x150f9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x150fe  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x15103  ldloc.s  7
0x15105  ldstr    aExchangeentryi// "exchangeentryid"
0x1510a  ldloc.s  4
0x1510c  ldloc.s  4
0x1510e  ldstr    aExchangeentryi_3// "ExchangeEntryId"
0x15113  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x15118  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x1511d  brtrue.s loc_15132
0x1511f  ldloc.s  4
0x15121  ldstr    aExchangeentryi_3// "ExchangeEntryId"
0x15126  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1512b  castclass [mscorlib]System.String
0x15130  br.s     loc_15137
0x15132  ldsfld   string [mscorlib]System.String::Empty
0x15137  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1513c  ldloc.0
0x1513d  ldloc.s  7
0x1513f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x15144  ldloc.s  4
0x15146  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x1514b  brtrue   loc_1507F
0x15150  leave.s  loc_15191
0x15152  stloc.s  8
0x15154  ldnull
0x15155  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x1515a  ldc.i4.6
0x1515b  ldstr    a01_2// "{0} - {1}"
0x15160  ldc.i4.2
0x15161  newarr   [mscorlib]System.Object
0x15166  dup
0x15167  ldc.i4.0
0x15168  ldstr    aResourcebookin_14// "ResourceBookingsWithChangedUserToDelete"...
0x1516d  stelem.ref
0x1516e  dup
0x1516f  ldc.i4.1
0x15170  ldloc.s  8
0x15172  callvirt instance string [mscorlib]System.Exception::get_Message()
0x15177  stelem.ref
0x15178  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1517d  leave.s  loc_15191
0x1517f  ldloc.s  4
0x15181  callvirt instance void [System.Data]System.Data.IDataReader::Close()
0x15186  endfinally
0x15187  ldloc.1
0x15188  brfalse.s loc_15190
0x1518a  ldloc.1
0x1518b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15190  endfinally
0x15191  ldloc.0
0x15192  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x15197  ldc.i4.0
0x15198  bgt.s    loc_1519C
0x1519a  ldnull
0x1519b  ret
0x1519c  ldloc.0
0x1519d  ret
```
