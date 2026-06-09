# SubscriptionTrackingDeletedObjectQuerySQL::Retrieve

- ea: `0x14dd0`
- end: `0x14ee4`
- name: `SubscriptionTrackingDeletedObjectQuerySQL::Retrieve`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x8ab0`
- `0x14dd0`

## string_xrefs

- `0x14e02`: `SELECT \n								SubscriptionTrackingDeletedObject.ObjectId FROM SubscriptionTrackingDeletedObject\n								WHERE SubscriptionTrackingDeletedObject.ObjectTypeCode = @objectTypeCode\n								AND SubscriptionTrackingDeletedObject.TimeStamp > @minVersionNumber`
- `0x14e9d`: `SubscriptionTrackingDeletedObjectQuerySQL`

## pseudocode

```c

```

## disassembly

```asm
0x14dd0  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x14dd5  stloc.0
0x14dd6  ldarg.0
0x14dd7  ldfld    valuetype [mscorlib]System.Guid SubscriptionTrackingDeletedObjectQuerySQL::organizationId
0x14ddc  ldc.i4.0
0x14ddd  ldc.i4.0
0x14dde  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x14de3  stloc.1
0x14de4  ldloc.1
0x14de5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x14dea  ldloc.1
0x14deb  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x14df0  stloc.2
0x14df1  ldloc.2
0x14df2  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x14df7  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0x14dfc  dup
0x14dfd  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x14e02  ldstr    aSelectSubscrip// "SELECT \r\n\t\t\t\t\t\t\t\tSubscription"...
0x14e07  stloc.3
0x14e08  dup
0x14e09  ldstr    aObjecttypecode// "@objectTypeCode"
0x14e0e  ldarg.0
0x14e0f  ldfld    int32 SubscriptionTrackingDeletedObjectQuerySQL::objectTypeCode
0x14e14  box      [mscorlib]System.Int32
0x14e19  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14e1e  pop
0x14e1f  ldstr    aMinversionnumb// "@minVersionNumber"
0x14e24  ldarg.0
0x14e25  ldfld    int64 SubscriptionTrackingDeletedObjectQuerySQL::minVersionNumber
0x14e2a  box      [mscorlib]System.Int64
0x14e2f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x14e34  pop
0x14e35  ldloc.2
0x14e36  ldloc.3
0x14e37  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x14e3c  ldloc.2
0x14e3d  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x14e42  stloc.s  4
0x14e44  br.s     loc_14E7C
0x14e46  ldstr    aBookableresour_4// "bookableresourcebooking"
0x14e4b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x14e50  stloc.s  5
0x14e52  ldloc.s  5
0x14e54  ldstr    aBookableresour_1// "bookableresourcebookingid"
0x14e59  ldloc.s  4
0x14e5b  ldstr    aObjectid// "ObjectId"
0x14e60  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x14e65  unbox.any [mscorlib]System.Guid
0x14e6a  box      [mscorlib]System.Guid
0x14e6f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x14e74  ldloc.0
0x14e75  ldloc.s  5
0x14e77  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x14e7c  ldloc.s  4
0x14e7e  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x14e83  brtrue.s loc_14E46
0x14e85  leave.s  loc_14ED7
0x14e87  stloc.s  6
0x14e89  ldnull
0x14e8a  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x14e8f  ldc.i4.6
0x14e90  ldstr    a01_2// "{0} - {1}"
0x14e95  ldc.i4.2
0x14e96  newarr   [mscorlib]System.Object
0x14e9b  dup
0x14e9c  ldc.i4.0
0x14e9d  ldstr    aSubscriptiontr// "SubscriptionTrackingDeletedObjectQueryS"...
0x14ea2  stelem.ref
0x14ea3  dup
0x14ea4  ldc.i4.1
0x14ea5  ldloc.s  6
0x14ea7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x14eac  stelem.ref
0x14ead  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14eb2  leave.s  loc_14ED7
0x14eb4  ldloc.s  4
0x14eb6  callvirt instance void [System.Data]System.Data.IDataReader::Close()
0x14ebb  endfinally
0x14ebc  ldloc.2
0x14ebd  brfalse.s loc_14EC5
0x14ebf  ldloc.2
0x14ec0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14ec5  endfinally
0x14ec6  ldloc.1
0x14ec7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x14ecc  endfinally
0x14ecd  ldloc.1
0x14ece  brfalse.s loc_14ED6
0x14ed0  ldloc.1
0x14ed1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14ed6  endfinally
0x14ed7  ldloc.0
0x14ed8  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x14edd  ldc.i4.0
0x14ede  bgt.s    loc_14EE2
0x14ee0  ldnull
0x14ee1  ret
0x14ee2  ldloc.0
0x14ee3  ret
```
