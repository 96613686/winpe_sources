# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::LogDeletionFailure

- ea: `0x1270`
- end: `0x1445`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::LogDeletionFailure`
- size: `469`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1fb0`
- `0x2fb0`
- `0x1f350`

## callees

- `0x1270`

## string_xrefs

- `0x1276`: `SELECT BulkDeleteOperationId FROM BulkDeleteOperationBase WHERE AsyncOperationId = @asyncOperationId`
- `0x12e2`: `INSERT INTO BulkDeleteFailureBase (BulkDeleteOperationId, AsyncOperationId, BulkDeleteFailureId, ErrorNumber, ErrorDescription, OrderedQueryIndex, RegardingObjectId, RegardingObjectTypeCode) SELECT @bulkDeleteOperationId, @asyncOperationId, NewId(), @crmErrorCode, @errorDescription, @orderedQueryIndex, @regardingObjectId, @entityType FROM {0} AS ENTTABLE WHERE ENTTABLE.{1}=@regardingObjectId`
- `0x1342`: `INSERT INTO BulkDeleteFailureBase (BulkDeleteOperationId, AsyncOperationId, BulkDeleteFailureId, ErrorNumber, ErrorDescription, OrderedQueryIndex, RegardingObjectId, RegardingObjectTypeCode, RegardingObjectIdName) SELECT @bulkDeleteOperationId, @asyncOperationId, NewId(), @crmErrorCode, @errorDescription, @orderedQueryIndex, @regardingObjectId, @entityType, ENTTABLE.{0} FROM {1} AS ENTTABLE WHERE ENTTABLE.{2}=@regardingObjectId`
- `0x13a2`: `INSERT INTO BulkDeleteFailureBase (BulkDeleteOperationId, AsyncOperationId, BulkDeleteFailureId, ErrorNumber, ErrorDescription, OrderedQueryIndex) VALUES (@bulkDeleteOperationId, @asyncOperationId, NewId(), @crmErrorCode, @errorDescription, @orderedQueryIndex)`
- `0x13af`: `@bulkDeleteOperationId`

## pseudocode

```c

```

## disassembly

```asm
0x1270  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1275  stloc.0
0x1276  ldstr    aSelectBulkdele// "SELECT BulkDeleteOperationId FROM BulkD"...
0x127b  ldc.i4.1
0x127c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x1281  stloc.1
0x1282  ldloc.1
0x1283  ldstr    aAsyncoperation// "@asyncOperationId"
0x1288  ldarg.1
0x1289  box      [mscorlib]System.Guid
0x128e  ldloca.s 4
0x1290  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1296  ldloc.s  4
0x1298  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x129d  ldarg.0
0x129e  ldloc.1
0x129f  ldarg.0
0x12a0  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x12a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x12aa  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x12af  stloc.2
0x12b0  ldloca.s 0
0x12b2  ldloc.2
0x12b3  callvirt instance string [mscorlib]System.Object::ToString()
0x12b8  call     instance void [mscorlib]System.Guid::.ctor(string)
0x12bd  ldsfld   string [mscorlib]System.String::Empty
0x12c2  pop
0x12c3  ldarg.s  5
0x12c5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12ca  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12cf  brfalse  loc_13A2
0x12d4  ldarg.s  9
0x12d6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12db  brfalse.s loc_133D
0x12dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12e2  ldstr    aInsertIntoBulk// "INSERT INTO BulkDeleteFailureBase (Bulk"...
0x12e7  ldc.i4.2
0x12e8  newarr   [mscorlib]System.Object
0x12ed  dup
0x12ee  ldc.i4.0
0x12ef  ldarg.s  7
0x12f1  stelem.ref
0x12f2  dup
0x12f3  ldc.i4.1
0x12f4  ldarg.s  8
0x12f6  stelem.ref
0x12f7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12fc  ldc.i4.1
0x12fd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x1302  stloc.3
0x1303  ldloc.3
0x1304  ldstr    aRegardingobjec// "@regardingObjectId"
0x1309  ldarg.s  5
0x130b  box      [mscorlib]System.Guid
0x1310  ldloca.s 4
0x1312  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1318  ldloc.s  4
0x131a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x131f  ldloc.3
0x1320  ldstr    aEntitytype// "@entityType"
0x1325  ldarg.s  6
0x1327  box      [mscorlib]System.Int32
0x132c  ldloca.s 4
0x132e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1334  ldloc.s  4
0x1336  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x133b  br.s     loc_13AE
0x133d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1342  ldstr    aInsertIntoBulk_0// "INSERT INTO BulkDeleteFailureBase (Bulk"...
0x1347  ldc.i4.3
0x1348  newarr   [mscorlib]System.Object
0x134d  dup
0x134e  ldc.i4.0
0x134f  ldarg.s  9
0x1351  stelem.ref
0x1352  dup
0x1353  ldc.i4.1
0x1354  ldarg.s  7
0x1356  stelem.ref
0x1357  dup
0x1358  ldc.i4.2
0x1359  ldarg.s  8
0x135b  stelem.ref
0x135c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1361  ldc.i4.1
0x1362  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x1367  stloc.3
0x1368  ldloc.3
0x1369  ldstr    aRegardingobjec// "@regardingObjectId"
0x136e  ldarg.s  5
0x1370  box      [mscorlib]System.Guid
0x1375  ldloca.s 4
0x1377  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x137d  ldloc.s  4
0x137f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x1384  ldloc.3
0x1385  ldstr    aEntitytype// "@entityType"
0x138a  ldarg.s  6
0x138c  box      [mscorlib]System.Int32
0x1391  ldloca.s 4
0x1393  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1399  ldloc.s  4
0x139b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x13a0  br.s     loc_13AE
0x13a2  ldstr    aInsertIntoBulk_1// "INSERT INTO BulkDeleteFailureBase (Bulk"...
0x13a7  ldc.i4.1
0x13a8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x13ad  stloc.3
0x13ae  ldloc.3
0x13af  ldstr    aBulkdeleteoper// "@bulkDeleteOperationId"
0x13b4  ldloc.0
0x13b5  box      [mscorlib]System.Guid
0x13ba  ldloca.s 4
0x13bc  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x13c2  ldloc.s  4
0x13c4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x13c9  ldloc.3
0x13ca  ldstr    aAsyncoperation// "@asyncOperationId"
0x13cf  ldarg.1
0x13d0  box      [mscorlib]System.Guid
0x13d5  ldloca.s 4
0x13d7  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x13dd  ldloc.s  4
0x13df  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x13e4  ldloc.3
0x13e5  ldstr    aCrmerrorcode// "@crmErrorCode"
0x13ea  ldarg.2
0x13eb  box      [mscorlib]System.Int32
0x13f0  ldloca.s 4
0x13f2  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x13f8  ldloc.s  4
0x13fa  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x13ff  ldloc.3
0x1400  ldstr    aErrordescripti// "@errorDescription"
0x1405  ldarg.3
0x1406  ldloca.s 4
0x1408  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x140e  ldloc.s  4
0x1410  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x1415  ldloc.3
0x1416  ldstr    aOrderedqueryin// "@orderedQueryIndex"
0x141b  ldarg.s  4
0x141d  box      [mscorlib]System.Int32
0x1422  ldloca.s 4
0x1424  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x142a  ldloc.s  4
0x142c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x1431  ldarg.0
0x1432  ldloc.3
0x1433  ldarg.0
0x1434  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x1439  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x143e  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x1443  pop
0x1444  ret
```
