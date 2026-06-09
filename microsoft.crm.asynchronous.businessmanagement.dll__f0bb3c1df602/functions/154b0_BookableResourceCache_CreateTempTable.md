# BookableResourceCache::CreateTempTable

- ea: `0x154b0`
- end: `0x1568f`
- name: `BookableResourceCache::CreateTempTable`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x14710`

## callees

- `0x8ab0`
- `0x154b0`
- `0x178d0`
- `0x178f0`
- `0x17950`

## string_xrefs

- `0x1550c`: `d:\dbs\sh\dccm2\1101_190851\cmd\77\src\Core\ObjectModel\Async\Handlers\BusinessManagement\ResourceBookingSyncService.cs`
- `0x15622`: `d:\dbs\sh\dccm2\1101_190851\cmd\77\src\Core\ObjectModel\Async\Handlers\BusinessManagement\ResourceBookingSyncService.cs`
- `0x154c0`: `CREATE TABLE #{0} (`
- `0x15507`: `CreateTempTable`
- `0x1561d`: `CreateTempTable`
- `0x15671`: `Create BookableResourceCache Temp Table {0}`

## pseudocode

```c

```

## disassembly

```asm
0x154b0  ldnull
0x154b1  stloc.0
0x154b2  ldarg.1
0x154b3  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x154b8  stloc.3
0x154b9  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x154be  stloc.0
0x154bf  ldloc.0
0x154c0  ldstr    aCreateTable0// "CREATE TABLE #{0} ("
0x154c5  ldarg.2
0x154c6  call     string [mscorlib]System.String::Format(string, object)
0x154cb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x154d0  pop
0x154d1  ldloc.0
0x154d2  ldstr    aBookableresour_13// "BookableResourceId uniqueidentifier PRI"...
0x154d7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x154dc  pop
0x154dd  ldloc.0
0x154de  ldstr    aUseridUniqueid// "UserId uniqueidentifier,"
0x154e3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x154e8  pop
0x154e9  ldloc.0
0x154ea  ldstr    aLastsyncversio// "LastSyncVersionNumber bigint)"
0x154ef  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x154f4  pop
0x154f5  ldloc.3
0x154f6  ldloc.0
0x154f7  callvirt instance string [mscorlib]System.Object::ToString()
0x154fc  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x15501  ldloc.3
0x15502  ldc.i4   0xBFF
0x15507  ldstr    aCreatetemptabl// "CreateTempTable"
0x1550c  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x15511  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x15516  pop
0x15517  leave.s  loc_15523
0x15519  ldloc.3
0x1551a  brfalse.s loc_15522
0x1551c  ldloc.3
0x1551d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15522  endfinally
0x15523  ldc.i4.0
0x15524  stloc.1
0x15525  ldc.i4.1
0x15526  stloc.2
0x15527  ldarg.0
0x15528  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData> BookableResourceCache::cacheByBookableResourceId
0x1552d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData>::get_Values()
0x15532  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype [mscorlib]System.Guid, class CacheData>::GetEnumerator()
0x15537  stloc.s  4
0x15539  br       loc_1563D
0x1553e  ldloca.s 4
0x15540  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class CacheData>::get_Current()
0x15545  stloc.s  5
0x15547  ldloc.2
0x15548  brfalse.s loc_15564
0x1554a  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1554f  stloc.0
0x15550  ldloc.0
0x15551  ldstr    aInsertInto0Val// "INSERT INTO #{0} VALUES"
0x15556  ldarg.2
0x15557  call     string [mscorlib]System.String::Format(string, object)
0x1555c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x15561  pop
0x15562  ldc.i4.0
0x15563  stloc.2
0x15564  ldloc.1
0x15565  ldc.i4.1
0x15566  add
0x15567  stloc.1
0x15568  ldloc.0
0x15569  ldstr    a0123// "('{0}', '{1}', {2}){3}"
0x1556e  ldc.i4.4
0x1556f  newarr   [mscorlib]System.Object
0x15574  dup
0x15575  ldc.i4.0
0x15576  ldloc.s  5
0x15578  callvirt instance valuetype [mscorlib]System.Guid CacheData::get_BookableResourceId()
0x1557d  stloc.s  6
0x1557f  ldloca.s 6
0x15581  constrained. [mscorlib]System.Guid
0x15587  callvirt instance string [mscorlib]System.Object::ToString()
0x1558c  stelem.ref
0x1558d  dup
0x1558e  ldc.i4.1
0x1558f  ldloc.s  5
0x15591  callvirt instance valuetype [mscorlib]System.Guid CacheData::get_UserId()
0x15596  stloc.s  6
0x15598  ldloca.s 6
0x1559a  constrained. [mscorlib]System.Guid
0x155a0  callvirt instance string [mscorlib]System.Object::ToString()
0x155a5  stelem.ref
0x155a6  dup
0x155a7  ldc.i4.2
0x155a8  ldloc.s  5
0x155aa  callvirt instance int64 CacheData::get_LastSyncVersionNumber()
0x155af  box      [mscorlib]System.Int64
0x155b4  stelem.ref
0x155b5  dup
0x155b6  ldc.i4.3
0x155b7  ldloc.1
0x155b8  ldarg.0
0x155b9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData> BookableResourceCache::cacheByBookableResourceId
0x155be  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData>::get_Values()
0x155c3  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype [mscorlib]System.Guid, class CacheData>::get_Count()
0x155c8  bge.s    loc_155D0
0x155ca  ldloc.1
0x155cb  ldc.i4.s 0x64
0x155cd  rem
0x155ce  brtrue.s loc_155D7
0x155d0  ldstr    asc_238BC// ""
0x155d5  br.s     loc_155DC
0x155d7  ldstr    asc_20444// ", "
0x155dc  stelem.ref
0x155dd  call     string [mscorlib]System.String::Format(string, object[])
0x155e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x155e7  pop
0x155e8  ldloc.1
0x155e9  ldc.i4.s 0x64
0x155eb  rem
0x155ec  brfalse.s loc_15601
0x155ee  ldloc.1
0x155ef  ldarg.0
0x155f0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData> BookableResourceCache::cacheByBookableResourceId
0x155f5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class CacheData>::get_Values()
0x155fa  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype [mscorlib]System.Guid, class CacheData>::get_Count()
0x155ff  blt.s    loc_1563D
0x15601  ldarg.1
0x15602  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x15607  stloc.s  7
0x15609  ldloc.s  7
0x1560b  ldloc.0
0x1560c  callvirt instance string [mscorlib]System.Object::ToString()
0x15611  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x15616  ldloc.s  7
0x15618  ldc.i4   0xC1C
0x1561d  ldstr    aCreatetemptabl// "CreateTempTable"
0x15622  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x15627  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1562c  pop
0x1562d  leave.s  loc_1563B
0x1562f  ldloc.s  7
0x15631  brfalse.s loc_1563A
0x15633  ldloc.s  7
0x15635  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1563a  endfinally
0x1563b  ldc.i4.1
0x1563c  stloc.2
0x1563d  ldloca.s 4
0x1563f  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class CacheData>::MoveNext()
0x15644  brtrue   loc_1553E
0x15649  leave.s  loc_15659
0x1564b  ldloca.s 4
0x1564d  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class CacheData>
0x15653  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15658  endfinally
0x15659  leave.s  loc_1568E
0x1565b  stloc.s  8
0x1565d  ldnull
0x1565e  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x15663  ldc.i4.6
0x15664  ldstr    a01_2// "{0} - {1}"
0x15669  ldc.i4.2
0x1566a  newarr   [mscorlib]System.Object
0x1566f  dup
0x15670  ldc.i4.0
0x15671  ldstr    aCreateBookable// "Create BookableResourceCache Temp Table"...
0x15676  ldarg.2
0x15677  call     string [mscorlib]System.String::Format(string, object)
0x1567c  stelem.ref
0x1567d  dup
0x1567e  ldc.i4.1
0x1567f  ldloc.s  8
0x15681  callvirt instance string [mscorlib]System.Exception::get_Message()
0x15686  stelem.ref
0x15687  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1568c  leave.s  loc_1568E
0x1568e  ret
```
