# Microsoft.Crm.Platform.SolutionAwareComponents.SolutionAwareEntitySyncHelper::AddEntryToTrackingDeletedObjects

- ea: `0x315b0`
- end: `0x3166a`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.SolutionAwareEntitySyncHelper::AddEntryToTrackingDeletedObjects`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x31500`

## callees

- `0x315b0`
- `0x31760`
- `0x67920`

## string_xrefs

- `0x315c5`: `insert into [SubscriptionTrackingDeletedObject] ([ObjectId], [ObjectTypeCode], [IsLogicalDelete]) VALUES (@ObjectId, @EntityObjectTypeCode, 1)`
- `0x31600`: `AddEntryToTrackingDeletedObjects`
- `0x31605`: `D:\a\1\s\src\ManagedPlatform\Server\SolutionAwareComponents\SolutionAwareEntitySyncHelper.cs`
- `0x31628`: `State transition failed to insert logical row in SubscriptionTrackingDeletedObject. Exception: {0}\nInnerException: {1}\nStack trace:\n{2}.`

## pseudocode

```c

```

## disassembly

```asm
0x315b0  ldarg.2
0x315b1  call     bool Microsoft.Crm.Platform.SolutionAwareComponents.SolutionAwareEntitySyncHelper::VerifyIfSubscriptionTrackingHasLogicalDeleteField(class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x315b6  brtrue.s loc_315BD
0x315b8  leave    loc_31669
0x315bd  ldarg.2
0x315be  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x315c3  stloc.0
0x315c4  ldloc.0
0x315c5  ldstr    aInsertIntoSubs// "insert into [SubscriptionTrackingDelete"...
0x315ca  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x315cf  ldloc.0
0x315d0  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x315d5  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x315da  dup
0x315db  ldstr    aObjectid_3// "@ObjectId"
0x315e0  ldarg.1
0x315e1  box      [mscorlib]System.Guid
0x315e6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x315eb  pop
0x315ec  ldstr    aEntityobjectty// "@EntityObjectTypeCode"
0x315f1  ldarg.0
0x315f2  box      [mscorlib]System.Int32
0x315f7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x315fc  pop
0x315fd  ldloc.0
0x315fe  ldc.i4.s 0x6D
0x31600  ldstr    aAddentrytotrac// "AddEntryToTrackingDeletedObjects"
0x31605  ldstr    aDA1SSrcManaged_5// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x3160a  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x3160f  pop
0x31610  leave.s  loc_3161C
0x31612  ldloc.0
0x31613  brfalse.s loc_3161B
0x31615  ldloc.0
0x31616  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3161b  endfinally
0x3161c  leave.s  loc_31669
0x3161e  stloc.1
0x3161f  ldloc.1
0x31620  ldarg.2
0x31621  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x31626  ldc.i4.s 0x14
0x31628  ldstr    aStateTransitio// "State transition failed to insert logic"...
0x3162d  ldc.i4.3
0x3162e  newarr   [mscorlib]System.Object
0x31633  dup
0x31634  ldc.i4.0
0x31635  ldloc.1
0x31636  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3163b  stelem.ref
0x3163c  dup
0x3163d  ldc.i4.1
0x3163e  ldloc.1
0x3163f  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x31644  brfalse.s loc_31653
0x31646  ldloc.1
0x31647  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x3164c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x31651  br.s     loc_31658
0x31653  ldsfld   string [mscorlib]System.String::Empty
0x31658  stelem.ref
0x31659  dup
0x3165a  ldc.i4.2
0x3165b  ldloc.1
0x3165c  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x31661  stelem.ref
0x31662  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x31667  leave.s  loc_31669
0x31669  ret
```
