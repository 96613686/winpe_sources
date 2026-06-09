# ResourceBookingsToDeleteForRetryQuerySQL::InitQuery

- ea: `0x149a0`
- end: `0x14a86`
- name: `ResourceBookingsToDeleteForRetryQuerySQL::InitQuery`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x143e0`

## string_xrefs

- `0x14a22`: `@isDeletedInExchange`
- `0x149e6`: `WHERE BookableResourceBookingExchangeSyncIdMapping.IsDeletedInExchange = @isDeletedInExchange`

## pseudocode

```c

```

## disassembly

```asm
0x149a0  ldarg.1
0x149a1  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x149a6  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x149ab  ldarg.2
0x149ac  ldstr    aSelectBookable_0// "SELECT BookableResourceBookingExchangeS"...
0x149b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x149b6  pop
0x149b7  ldarg.2
0x149b8  ldstr    aBookableresour_6// "BookableResourceBookingExchangeSyncIdMa"...
0x149bd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x149c2  pop
0x149c3  ldarg.2
0x149c4  ldstr    aBookableresour_7// "BookableResourceBookingExchangeSyncIdMa"...
0x149c9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x149ce  pop
0x149cf  ldarg.2
0x149d0  ldstr    aFromBookablere_0// "FROM BookableResourceBookingExchangeSyn"...
0x149d5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x149da  pop
0x149db  ldarg.0
0x149dc  ldarg.1
0x149dd  ldarg.2
0x149de  callvirt instance class [mscorlib]System.Text.StringBuilder ResourceBookingPagedEntitySQLQuery::AddJoinTempTableToQuery(class [System.Data]System.Data.IDbCommand command, class [mscorlib]System.Text.StringBuilder query)
0x149e3  starg.s  2
0x149e5  ldarg.2
0x149e6  ldstr    aWhereBookabler_6// "WHERE BookableResourceBookingExchangeSy"...
0x149eb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x149f0  pop
0x149f1  ldarg.2
0x149f2  ldstr    aAndBookableres_6// "AND BookableResourceBookingExchangeSync"...
0x149f7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x149fc  pop
0x149fd  ldarg.2
0x149fe  ldstr    aAndBookableres_7// "AND BookableResourceBookingExchangeSync"...
0x14a03  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14a08  pop
0x14a09  ldarg.2
0x14a0a  ldstr    aAndBookableres_9// "AND (BookableResourceBookingExchangeSyn"...
0x14a0f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14a14  pop
0x14a15  ldarg.2
0x14a16  ldstr    aOrBookablereso_1// "OR BookableResourceBookingExchangeSyncI"...
0x14a1b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14a20  pop
0x14a21  dup
0x14a22  ldstr    aIsdeletedinexc_2// "@isDeletedInExchange"
0x14a27  ldc.i4.1
0x14a28  box      [mscorlib]System.Int32
0x14a2d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14a32  pop
0x14a33  dup
0x14a34  ldstr    aModifedbefored// "@modifedBeforeDateTime"
0x14a39  ldarg.0
0x14a3a  ldfld    valuetype [mscorlib]System.DateTime ResourceBookingsToDeleteForRetryQuerySQL::modifiedBeforeDateTime
0x14a3f  box      [mscorlib]System.DateTime
0x14a44  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14a49  pop
0x14a4a  dup
0x14a4b  ldstr    aMaxretrycount_0// "@maxRetryCount"
0x14a50  ldarg.0
0x14a51  ldfld    int32 ResourceBookingsToDeleteForRetryQuerySQL::maxRetryCount
0x14a56  box      [mscorlib]System.Int32
0x14a5b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14a60  pop
0x14a61  dup
0x14a62  ldstr    aSyncstatusretr// "@syncStatusRetry"
0x14a67  ldc.i4.1
0x14a68  box      [mscorlib]System.Int32
0x14a6d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14a72  pop
0x14a73  ldstr    aSyncstatuspend// "@syncStatusPending"
0x14a78  ldc.i4.2
0x14a79  box      [mscorlib]System.Int32
0x14a7e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14a83  pop
0x14a84  ldarg.2
0x14a85  ret
```
