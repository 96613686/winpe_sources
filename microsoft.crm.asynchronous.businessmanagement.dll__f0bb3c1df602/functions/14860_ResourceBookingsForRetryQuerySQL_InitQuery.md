# ResourceBookingsForRetryQuerySQL::InitQuery

- ea: `0x14860`
- end: `0x14932`
- name: `ResourceBookingsForRetryQuerySQL::InitQuery`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x143a0`
- `0x143e0`

## string_xrefs

- `0x148d4`: `AND BookableResourceBookingExchangeSyncIdMapping.IsDeletedInExchange = @isDeletedInExchange`
- `0x1491f`: `@isDeletedInExchange`

## pseudocode

```c

```

## disassembly

```asm
0x14860  ldarg.1
0x14861  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x14866  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1486b  ldarg.0
0x1486c  ldarg.1
0x1486d  ldarg.2
0x1486e  call     instance class [mscorlib]System.Text.StringBuilder ResourceBookingPagedEntitySQLQuery::InitQuery(class [System.Data]System.Data.IDbCommand command, class [mscorlib]System.Text.StringBuilder query)
0x14873  starg.s  2
0x14875  ldarg.0
0x14876  ldarg.1
0x14877  ldarg.2
0x14878  callvirt instance class [mscorlib]System.Text.StringBuilder ResourceBookingPagedEntitySQLQuery::AddJoinTempTableToQuery(class [System.Data]System.Data.IDbCommand command, class [mscorlib]System.Text.StringBuilder query)
0x1487d  starg.s  2
0x1487f  ldarg.2
0x14880  ldstr    aJoinBookablere_0// "JOIN BookableResourceBookingExchangeSyn"...
0x14885  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1488a  pop
0x1488b  ldarg.2
0x1488c  ldstr    aOnBookablereso_0// "ON BookableResourceBookingExchangeSyncI"...
0x14891  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x14896  pop
0x14897  ldarg.2
0x14898  ldstr    aWhereBookabler_5// "WHERE BookableResourceBooking.StartTime"...
0x1489d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x148a2  pop
0x148a3  ldarg.2
0x148a4  ldstr    aAndBookableres_3// "AND BookableResourceBooking.EndTime IS "...
0x148a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x148ae  pop
0x148af  ldarg.2
0x148b0  ldstr    aAndBookableres_5// "AND BookableResourceBookingExchangeSync"...
0x148b5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x148ba  pop
0x148bb  ldarg.2
0x148bc  ldstr    aAndBookableres_6// "AND BookableResourceBookingExchangeSync"...
0x148c1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x148c6  pop
0x148c7  ldarg.2
0x148c8  ldstr    aAndBookableres_7// "AND BookableResourceBookingExchangeSync"...
0x148cd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x148d2  pop
0x148d3  ldarg.2
0x148d4  ldstr    aAndBookableres_8// "AND BookableResourceBookingExchangeSync"...
0x148d9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x148de  pop
0x148df  dup
0x148e0  ldstr    aSyncstatus// "@syncStatus"
0x148e5  ldc.i4.1
0x148e6  box      [mscorlib]System.Int32
0x148eb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x148f0  pop
0x148f1  dup
0x148f2  ldstr    aModifedbefored// "@modifedBeforeDateTime"
0x148f7  ldarg.0
0x148f8  ldfld    valuetype [mscorlib]System.DateTime ResourceBookingsForRetryQuerySQL::modifiedBeforeDateTime
0x148fd  box      [mscorlib]System.DateTime
0x14902  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14907  pop
0x14908  dup
0x14909  ldstr    aMaxretrycount_0// "@maxRetryCount"
0x1490e  ldarg.0
0x1490f  ldfld    int32 ResourceBookingsForRetryQuerySQL::maxRetryCount
0x14914  box      [mscorlib]System.Int32
0x14919  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1491e  pop
0x1491f  ldstr    aIsdeletedinexc_2// "@isDeletedInExchange"
0x14924  ldc.i4.0
0x14925  box      [mscorlib]System.Int32
0x1492a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1492f  pop
0x14930  ldarg.2
0x14931  ret
```
