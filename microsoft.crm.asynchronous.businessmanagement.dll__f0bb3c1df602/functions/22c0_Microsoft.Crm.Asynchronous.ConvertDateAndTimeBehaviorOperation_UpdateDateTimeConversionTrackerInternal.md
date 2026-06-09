# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateDateTimeConversionTrackerInternal

- ea: `0x22c0`
- end: `0x23fa`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateDateTimeConversionTrackerInternal`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x21c0`
- `0x2900`

## callees

- `0x22c0`

## string_xrefs

- `0x22c6`: `UPDATE [dbo].[DateTimeConversionTracker] SET [Status] = {0},[ModifiedOn] = {1} WHERE EntityId = {2} AND AttributeId = {3}`
- `0x2391`: `UpdateDateTimeConversionTrackerInternal`
- `0x23aa`: `AsyncHandler::ConvertDateAndTimeBehaviorOperation:Exception occured during update of DateTimeConversionTracker entry for Entity: {0} Attribute : {1} Exception : {2}`

## pseudocode

```c

```

## disassembly

```asm
0x22c0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::.ctor()
0x22c5  stloc.0
0x22c6  ldstr    aUpdateDboDatet// "UPDATE [dbo].[DateTimeConversionTracker"...
0x22cb  stloc.1
0x22cc  ldstr    aAttributeid// "AttributeId"
0x22d1  stloc.2
0x22d2  ldloc.0
0x22d3  ldloc.2
0x22d4  ldarg.s  5
0x22d6  box      [mscorlib]System.Guid
0x22db  ldc.i4.s 0xE
0x22dd  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, valuetype [System.Data]System.Data.SqlDbType)
0x22e2  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0x22e7  stloc.3
0x22e8  ldstr    aEntityid// "EntityId"
0x22ed  stloc.s  4
0x22ef  ldloc.0
0x22f0  ldloc.s  4
0x22f2  ldarg.3
0x22f3  box      [mscorlib]System.Guid
0x22f8  ldc.i4.s 0xE
0x22fa  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, valuetype [System.Data]System.Data.SqlDbType)
0x22ff  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0x2304  stloc.s  5
0x2306  ldstr    aStatus// "Status"
0x230b  stloc.s  6
0x230d  ldloc.0
0x230e  ldloc.s  6
0x2310  ldarg.s  6
0x2312  box      [mscorlib]System.Int32
0x2317  ldc.i4.8
0x2318  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, valuetype [System.Data]System.Data.SqlDbType)
0x231d  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0x2322  stloc.s  7
0x2324  ldstr    aModifiedon_0// "ModifiedOn"
0x2329  stloc.s  8
0x232b  ldloc.0
0x232c  ldloc.s  8
0x232e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x2333  box      [mscorlib]System.DateTime
0x2338  ldc.i4.4
0x2339  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, valuetype [System.Data]System.Data.SqlDbType)
0x233e  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0x2343  stloc.s  9
0x2345  ldarg.1
0x2346  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x234b  stloc.s  0xA
0x234d  ldloc.0
0x234e  ldloc.s  0xA
0x2350  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2355  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x235a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParametersToSqlParameterCollection(class [System.Data]System.Data.SqlClient.SqlParameterCollection)
0x235f  ldloc.s  0xA
0x2361  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2366  ldloc.1
0x2367  ldc.i4.4
0x2368  newarr   [mscorlib]System.Object
0x236d  dup
0x236e  ldc.i4.0
0x236f  ldloc.s  7
0x2371  stelem.ref
0x2372  dup
0x2373  ldc.i4.1
0x2374  ldloc.s  9
0x2376  stelem.ref
0x2377  dup
0x2378  ldc.i4.2
0x2379  ldloc.s  5
0x237b  stelem.ref
0x237c  dup
0x237d  ldc.i4.3
0x237e  ldloc.3
0x237f  stelem.ref
0x2380  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2385  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x238a  ldloc.s  0xA
0x238c  ldc.i4   0xBA
0x2391  ldstr    aUpdatedatetime// "UpdateDateTimeConversionTrackerInternal"
0x2396  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x239b  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x23a0  pop
0x23a1  leave.s  loc_23F9
0x23a3  stloc.s  0xB
0x23a5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23aa  ldstr    aAsynchandlerCo_1// "AsyncHandler::ConvertDateAndTimeBehavio"...
0x23af  ldc.i4.3
0x23b0  newarr   [mscorlib]System.Object
0x23b5  dup
0x23b6  ldc.i4.0
0x23b7  ldarg.2
0x23b8  stelem.ref
0x23b9  dup
0x23ba  ldc.i4.1
0x23bb  ldarg.s  4
0x23bd  stelem.ref
0x23be  dup
0x23bf  ldc.i4.2
0x23c0  ldloc.s  0xB
0x23c2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x23c7  stelem.ref
0x23c8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x23cd  stloc.s  0xC
0x23cf  ldloc.s  0xB
0x23d1  ldarg.0
0x23d2  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_asyncEvent
0x23d7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x23dc  ldc.i4.s 0x15
0x23de  ldloc.s  0xC
0x23e0  ldc.i4.0
0x23e1  newarr   [mscorlib]System.Object
0x23e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x23eb  leave.s  loc_23F9
0x23ed  ldloc.s  0xA
0x23ef  brfalse.s loc_23F8
0x23f1  ldloc.s  0xA
0x23f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23f8  endfinally
0x23f9  ret
```
