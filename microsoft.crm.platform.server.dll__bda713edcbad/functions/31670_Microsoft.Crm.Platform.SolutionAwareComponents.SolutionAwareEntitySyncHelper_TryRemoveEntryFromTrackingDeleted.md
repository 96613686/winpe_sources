# Microsoft.Crm.Platform.SolutionAwareComponents.SolutionAwareEntitySyncHelper::TryRemoveEntryFromTrackingDeletedObjects

- ea: `0x31670`
- end: `0x3172d`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.SolutionAwareEntitySyncHelper::TryRemoveEntryFromTrackingDeletedObjects`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x31500`

## callees

- `0x31670`
- `0x31760`
- `0x67920`

## string_xrefs

- `0x316c8`: `D:\a\1\s\src\ManagedPlatform\Server\SolutionAwareComponents\SolutionAwareEntitySyncHelper.cs`
- `0x31685`: `delete from [SubscriptionTrackingDeletedObject] where [ObjectId] = @ObjectId and [ObjectTypeCode] = @EntityObjectTypeCode and [IsLogicalDelete] = 1`
- `0x316c3`: `TryRemoveEntryFromTrackingDeletedObjects`
- `0x316eb`: `State transition failed to delete logical row from SubscriptionTrackingDeletedObject. Exception: {0}\nInnerException: {1}\nStack trace:\n{2}.`

## pseudocode

```c

```

## disassembly

```asm
0x31670  ldarg.2
0x31671  call     bool Microsoft.Crm.Platform.SolutionAwareComponents.SolutionAwareEntitySyncHelper::VerifyIfSubscriptionTrackingHasLogicalDeleteField(class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x31676  brtrue.s loc_3167D
0x31678  leave    loc_3172C
0x3167d  ldarg.2
0x3167e  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x31683  stloc.0
0x31684  ldloc.0
0x31685  ldstr    aDeleteFromSubs// "delete from [SubscriptionTrackingDelete"...
0x3168a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x3168f  ldloc.0
0x31690  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x31695  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x3169a  dup
0x3169b  ldstr    aObjectid_3// "@ObjectId"
0x316a0  ldarg.1
0x316a1  box      [mscorlib]System.Guid
0x316a6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x316ab  pop
0x316ac  ldstr    aEntityobjectty// "@EntityObjectTypeCode"
0x316b1  ldarg.0
0x316b2  box      [mscorlib]System.Int32
0x316b7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x316bc  pop
0x316bd  ldloc.0
0x316be  ldc.i4   0x8B
0x316c3  ldstr    aTryremoveentry// "TryRemoveEntryFromTrackingDeletedObject"...
0x316c8  ldstr    aDA1SSrcManaged_5// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x316cd  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x316d2  pop
0x316d3  leave.s  loc_316DF
0x316d5  ldloc.0
0x316d6  brfalse.s loc_316DE
0x316d8  ldloc.0
0x316d9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x316de  endfinally
0x316df  leave.s  loc_3172C
0x316e1  stloc.1
0x316e2  ldloc.1
0x316e3  ldarg.2
0x316e4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x316e9  ldc.i4.s 0x14
0x316eb  ldstr    aStateTransitio_0// "State transition failed to delete logic"...
0x316f0  ldc.i4.3
0x316f1  newarr   [mscorlib]System.Object
0x316f6  dup
0x316f7  ldc.i4.0
0x316f8  ldloc.1
0x316f9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x316fe  stelem.ref
0x316ff  dup
0x31700  ldc.i4.1
0x31701  ldloc.1
0x31702  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x31707  brfalse.s loc_31716
0x31709  ldloc.1
0x3170a  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x3170f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x31714  br.s     loc_3171B
0x31716  ldsfld   string [mscorlib]System.String::Empty
0x3171b  stelem.ref
0x3171c  dup
0x3171d  ldc.i4.2
0x3171e  ldloc.1
0x3171f  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x31724  stelem.ref
0x31725  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3172a  leave.s  loc_3172C
0x3172c  ret
```
