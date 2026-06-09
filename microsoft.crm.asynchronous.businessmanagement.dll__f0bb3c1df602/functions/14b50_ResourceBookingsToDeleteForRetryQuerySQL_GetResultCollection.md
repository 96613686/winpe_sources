# ResourceBookingsToDeleteForRetryQuerySQL::GetResultCollection

- ea: `0x14b50`
- end: `0x14c8a`
- name: `ResourceBookingsToDeleteForRetryQuerySQL::GetResultCollection`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x8ab0`
- `0x14190`
- `0x14b50`
- `0x15300`

## string_xrefs

- `0x14c5f`: `ResourceBookingsToDeleteForRetryQuerySQL`

## pseudocode

```c

```

## disassembly

```asm
0x14b50  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x14b55  stloc.0
0x14b56  br       loc_14C3C
0x14b5b  ldstr    aBookableresour// "bookableresourcebookingexchangesyncidma"...
0x14b60  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x14b65  stloc.1
0x14b66  ldarg.1
0x14b67  ldstr    aUserid_0// "UserId"
0x14b6c  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x14b71  unbox.any [mscorlib]System.Guid
0x14b76  stloc.2
0x14b77  ldarg.0
0x14b78  ldfld    class BookableResourceCache ResourceBookingPagedEntitySQLQuery::bookableResourceCache
0x14b7d  ldloc.2
0x14b7e  callvirt instance class CacheData BookableResourceCache::GetByUserId(valuetype [mscorlib]System.Guid userId)
0x14b83  ldarg.1
0x14b84  ldstr    aSyncversionnum_1// "SyncVersionNumber"
0x14b89  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x14b8e  unbox.any [mscorlib]System.Int64
0x14b93  stloc.3
0x14b94  ldarg.0
0x14b95  call     instance bool PagedEntitySQLQuery::get_IsPagingEnabled()
0x14b9a  brfalse.s loc_14BAA
0x14b9c  ldarg.0
0x14b9d  ldloc.2
0x14b9e  stfld    valuetype [mscorlib]System.Guid ResourceBookingPagedEntitySQLQuery::previousPageId
0x14ba3  ldarg.0
0x14ba4  ldloc.3
0x14ba5  stfld    int64 ResourceBookingPagedEntitySQLQuery::previousPageVersionNumber
0x14baa  brfalse  loc_14C3C
0x14baf  ldloc.1
0x14bb0  ldstr    aBookableresour// "bookableresourcebookingexchangesyncidma"...
0x14bb5  ldarg.1
0x14bb6  ldstr    aBookableresour_8// "BookableResourceBookingExchangeSyncIdMa"...
0x14bbb  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x14bc0  unbox.any [mscorlib]System.Guid
0x14bc5  box      [mscorlib]System.Guid
0x14bca  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14bcf  ldloc.1
0x14bd0  ldstr    aUserid// "userid"
0x14bd5  ldloc.2
0x14bd6  box      [mscorlib]System.Guid
0x14bdb  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14be0  ldloc.1
0x14be1  ldstr    aExchangeentryi// "exchangeentryid"
0x14be6  ldarg.1
0x14be7  ldarg.1
0x14be8  ldstr    aExchangeentryi_3// "ExchangeEntryId"
0x14bed  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetOrdinal(string)
0x14bf2  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0x14bf7  brtrue.s loc_14C0B
0x14bf9  ldarg.1
0x14bfa  ldstr    aExchangeentryi_3// "ExchangeEntryId"
0x14bff  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x14c04  castclass [mscorlib]System.String
0x14c09  br.s     loc_14C10
0x14c0b  ldsfld   string [mscorlib]System.String::Empty
0x14c10  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14c15  ldloc.1
0x14c16  ldstr    aSyncstatus_0// "syncstatus"
0x14c1b  ldarg.1
0x14c1c  ldstr    aSyncstatus_1// "SyncStatus"
0x14c21  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x14c26  unbox.any [mscorlib]System.Int32
0x14c2b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x14c30  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14c35  ldloc.0
0x14c36  ldloc.1
0x14c37  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x14c3c  ldarg.1
0x14c3d  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x14c42  brtrue   loc_14B5B
0x14c47  leave.s  loc_14C7D
0x14c49  stloc.s  4
0x14c4b  ldnull
0x14c4c  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x14c51  ldc.i4.6
0x14c52  ldstr    a01_2// "{0} - {1}"
0x14c57  ldc.i4.2
0x14c58  newarr   [mscorlib]System.Object
0x14c5d  dup
0x14c5e  ldc.i4.0
0x14c5f  ldstr    aResourcebookin_12// "ResourceBookingsToDeleteForRetryQuerySQ"...
0x14c64  stelem.ref
0x14c65  dup
0x14c66  ldc.i4.1
0x14c67  ldloc.s  4
0x14c69  callvirt instance string [mscorlib]System.Exception::get_Message()
0x14c6e  stelem.ref
0x14c6f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14c74  leave.s  loc_14C7D
0x14c76  ldarg.1
0x14c77  callvirt instance void [System.Data]System.Data.IDataReader::Close()
0x14c7c  endfinally
0x14c7d  ldloc.0
0x14c7e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x14c83  ldc.i4.0
0x14c84  bgt.s    loc_14C88
0x14c86  ldnull
0x14c87  ret
0x14c88  ldloc.0
0x14c89  ret
```
