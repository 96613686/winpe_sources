# ResourceBookingsPendingIdMappingQuerySQL::InitQuery

- ea: `0x14cd0`
- end: `0x14d96`
- name: `ResourceBookingsPendingIdMappingQuerySQL::InitQuery`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x143a0`
- `0x143e0`

## string_xrefs

- `0x14d38`: `AND BookableResourceBookingExchangeSyncIdMapping.IsDeletedInExchange = @isDeletedInExchange`
- `0x14d83`: `@isDeletedInExchange`

## pseudocode

```c

```

## disassembly

```asm
0x14cd0  ldarg.1
0x14cd1  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x14cd6  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x14cdb  ldarg.0
0x14cdc  ldarg.1
0x14cdd  ldarg.2
0x14cde  call     instance class [mscorlib]System.Text.StringBuilder ResourceBookingPagedEntitySQLQuery::InitQuery(class [System.Data]System.Data.IDbCommand command, class [mscorlib]System.Text.StringBuilder query)
0x14ce3  starg.s  2
0x14ce5  ldarg.0
0x14ce6  ldarg.1
0x14ce7  ldarg.2
0x14ce8  callvirt instance class [mscorlib]System.Text.StringBuilder ResourceBookingPagedEntitySQLQuery::AddJoinTempTableToQuery(class [System.Data]System.Data.IDbCommand command, class [mscorlib]System.Text.StringBuilder query)
0x14ced  starg.s  2
0x14cef  ldarg.2
0x14cf0  ldstr    aJoinBookablere_0// "JOIN BookableResourceBookingExchangeSyn"...
0x14cf5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14cfa  pop
0x14cfb  ldarg.2
0x14cfc  ldstr    aOnBookablereso_0// "ON BookableResourceBookingExchangeSyncI"...
0x14d01  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14d06  pop
0x14d07  ldarg.2
0x14d08  ldstr    aWhereBookabler_7// "WHERE BookableResourceBooking.StartTime"...
0x14d0d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14d12  pop
0x14d13  ldarg.2
0x14d14  ldstr    aAndBookableres_3// "AND BookableResourceBooking.EndTime IS "...
0x14d19  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14d1e  pop
0x14d1f  ldarg.2
0x14d20  ldstr    aAndBookableres_5// "AND BookableResourceBookingExchangeSync"...
0x14d25  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14d2a  pop
0x14d2b  ldarg.2
0x14d2c  ldstr    aAndBookableres_7// "AND BookableResourceBookingExchangeSync"...
0x14d31  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14d36  pop
0x14d37  ldarg.2
0x14d38  ldstr    aAndBookableres_8// "AND BookableResourceBookingExchangeSync"...
0x14d3d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14d42  pop
0x14d43  dup
0x14d44  ldstr    aUpperdatebound// "@upperDateBound"
0x14d49  ldarg.0
0x14d4a  ldfld    valuetype [mscorlib]System.DateTime ResourceBookingsPendingIdMappingQuerySQL::upperDateBound
0x14d4f  box      [mscorlib]System.DateTime
0x14d54  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14d59  pop
0x14d5a  dup
0x14d5b  ldstr    aSyncstatus// "@syncStatus"
0x14d60  ldc.i4.2
0x14d61  box      [mscorlib]System.Int32
0x14d66  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14d6b  pop
0x14d6c  dup
0x14d6d  ldstr    aMaxretrycount_0// "@maxRetryCount"
0x14d72  ldarg.0
0x14d73  ldfld    int32 ResourceBookingsPendingIdMappingQuerySQL::maxRetryCount
0x14d78  box      [mscorlib]System.Int32
0x14d7d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14d82  pop
0x14d83  ldstr    aIsdeletedinexc_2// "@isDeletedInExchange"
0x14d88  ldc.i4.0
0x14d89  box      [mscorlib]System.Int32
0x14d8e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14d93  pop
0x14d94  ldarg.2
0x14d95  ret
```
