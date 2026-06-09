# Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::PersistRecordsInMatchCodeTable

- ea: `0x1e830`
- end: `0x1ea54`
- name: `Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::PersistRecordsInMatchCodeTable`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1e680`

## callees

- `0x20`
- `0x1e830`
- `0x1ed50`
- `0x1f0f0`

## string_xrefs

- `0x1e85e`: `IF EXISTS (SELECT 1 FROM {0} WHERE ObjectId = @objectId)\n						UPDATE {0} SET MatchCode = @matchCode, \n								ModifiedOn = (SELECT ENTTABLE.ModifiedOn FROM {1} AS ENTTABLE \n												WHERE ENTTABLE.{2} = @objectId)\n								WHERE ObjectId = @objectId\n					  ELSE\n						INSERT INTO {0} (ObjectId, MatchCode, ModifiedOn) \n							SELECT @objectId, @matchCode, \n								ENTTABLE.ModifiedOn FROM {1} AS ENTTABLE WHERE ENTTABLE.{2} = @objectId`
- `0x1e975`: `Non breaking error encountered when inserting matchcode: Matchcode already exists in matchcode table`

## pseudocode

```c

```

## disassembly

```asm
0x1e830  ldarg.0
0x1e831  brfalse.s loc_1E849
0x1e833  ldarg.0
0x1e834  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1e839  brfalse.s loc_1E849
0x1e83b  ldarg.0
0x1e83c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1e841  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1e846  ldc.i4.0
0x1e847  bgt.s    loc_1E84B
0x1e849  ldnull
0x1e84a  ret
0x1e84b  ldnull
0x1e84c  stloc.0
0x1e84d  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x1e852  stloc.1
0x1e853  ldsfld   string [mscorlib]System.String::Empty
0x1e858  stloc.2
0x1e859  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e85e  ldstr    aIfExistsSelect_1// "IF EXISTS (SELECT 1 FROM {0} WHERE Obje"...
0x1e863  ldc.i4.3
0x1e864  newarr   [mscorlib]System.Object
0x1e869  dup
0x1e86a  ldc.i4.0
0x1e86b  ldarg.3
0x1e86c  stelem.ref
0x1e86d  dup
0x1e86e  ldc.i4.1
0x1e86f  ldarg.s  9
0x1e871  stelem.ref
0x1e872  dup
0x1e873  ldc.i4.2
0x1e874  ldarg.s  0xA
0x1e876  stelem.ref
0x1e877  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e87c  stloc.2
0x1e87d  ldloc.1
0x1e87e  ldloc.2
0x1e87f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1e884  ldloc.1
0x1e885  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1e88a  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1e88f  stloc.3
0x1e890  ldloc.3
0x1e891  ldstr    aObjectid_0// "@objectId"
0x1e896  ldsfld   string [mscorlib]System.String::Empty
0x1e89b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1e8a0  pop
0x1e8a1  ldloc.3
0x1e8a2  ldstr    aMatchcode// "@matchCode"
0x1e8a7  ldsfld   string [mscorlib]System.String::Empty
0x1e8ac  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1e8b1  pop
0x1e8b2  ldc.i4.0
0x1e8b3  stloc.s  4
0x1e8b5  br       loc_1EA31
0x1e8ba  ldarg.0
0x1e8bb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1e8c0  ldloc.s  4
0x1e8c2  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x1e8c7  stloc.s  5
0x1e8c9  ldloc.s  5
0x1e8cb  ldarg.1
0x1e8cc  ldarg.s  4
0x1e8ce  ldarg.s  8
0x1e8d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_OwnerId()
0x1e8d5  ldarg.s  8
0x1e8d7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1e8dc  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.UserAndOrganizationContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1e8e1  ldarg.s  0xB
0x1e8e3  call     string Microsoft.Crm.GenerateMC::GenerateMatchCode(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity dynamicEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ShareableDuplicateRule rule, bool mainEntityFlag, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext context, int32 maxMatchcodeLength)
0x1e8e8  stloc.0
0x1e8e9  ldloc.s  5
0x1e8eb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1e8f0  ldarg.2
0x1e8f1  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1e8f6  brfalse  loc_1E9B5
0x1e8fb  ldloc.s  5
0x1e8fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x1e902  stloc.s  6
0x1e904  ldloc.3
0x1e905  ldstr    aObjectid_0// "@objectId"
0x1e90a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x1e90f  ldloca.s 6
0x1e911  constrained. [mscorlib]System.Guid
0x1e917  callvirt instance string [mscorlib]System.Object::ToString()
0x1e91c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1e921  ldloc.0
0x1e922  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e927  brtrue.s loc_1E93C
0x1e929  ldloc.3
0x1e92a  ldstr    aMatchcode// "@matchCode"
0x1e92f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x1e934  ldloc.0
0x1e935  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1e93a  br.s     loc_1E951
0x1e93c  ldloc.3
0x1e93d  ldstr    aMatchcode// "@matchCode"
0x1e942  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x1e947  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1e94c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1e951  nop
0x1e952  ldarg.s  6
0x1e954  ldloc.1
0x1e955  callvirt instance void Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess::ExecuteCommand(class [System.Data]System.Data.IDbCommand command)
0x1e95a  leave.s  loc_1E9B0
0x1e95c  stloc.s  7
0x1e95e  ldloc.s  7
0x1e960  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x1e965  ldc.i4   0xA29
0x1e96a  bne.un.s loc_1E987
0x1e96c  ldarg.s  8
0x1e96e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1e973  ldc.i4.s 0x15
0x1e975  ldstr    aNonBreakingErr// "Non breaking error encountered when ins"...
0x1e97a  ldc.i4.0
0x1e97b  newarr   [mscorlib]System.Object
0x1e980  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e985  br.s     loc_1E9AE
0x1e987  ldloc.s  7
0x1e989  ldarg.s  8
0x1e98b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1e990  ldc.i4.s 0x15
0x1e992  ldstr    aErrorWhileInse// "Error while inserting/updating matchcod"...
0x1e997  ldc.i4.1
0x1e998  newarr   [mscorlib]System.Object
0x1e99d  dup
0x1e99e  ldc.i4.0
0x1e99f  ldloc.s  7
0x1e9a1  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1e9a6  stelem.ref
0x1e9a7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e9ac  rethrow
0x1e9ae  leave.s  loc_1E9B0
0x1e9b0  ldarg.s  0xC
0x1e9b2  ldloc.s  4
0x1e9b4  stind.i4
0x1e9b5  ldloc.s  4
0x1e9b7  ldc.i4.1
0x1e9b8  add
0x1e9b9  ldarg.s  5
0x1e9bb  rem
0x1e9bc  brtrue.s loc_1EA1F
0x1e9be  ldarg.s  8
0x1e9c0  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::QueryForEarlyExitRequest()
0x1e9c5  stloc.s  8
0x1e9c7  ldloc.s  8
0x1e9c9  ldc.i4.1
0x1e9ca  beq.s    loc_1E9D3
0x1e9cc  ldloc.s  8
0x1e9ce  ldc.i4.2
0x1e9cf  beq.s    loc_1E9DC
0x1e9d1  br.s     loc_1EA1F
0x1e9d3  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor()
0x1e9d8  stloc.s  9
0x1e9da  leave.s  loc_1EA51
0x1e9dc  ldarg.s  8
0x1e9de  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x1e9e3  ldc.i4.7
0x1e9e4  bne.un.s loc_1E9FC
0x1e9e6  ldarg.1
0x1e9e7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ShareableDuplicateRule::get_Id()
0x1e9ec  ldarg.s  6
0x1e9ee  ldarg.s  8
0x1e9f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1e9f5  ldarg.s  7
0x1e9f7  call     void Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::UnpublishRule(valuetype [mscorlib]System.Guid ruleId, class Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess data, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService)
0x1e9fc  ldnull
0x1e9fd  ldarg.s  8
0x1e9ff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1ea04  ldc.i4.s 0x15
0x1ea06  ldstr    aMethodPersistr// "Method: PersistRecordsInMatchCodeTable."...
0x1ea0b  ldc.i4.0
0x1ea0c  newarr   [mscorlib]System.Object
0x1ea11  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ea16  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor()
0x1ea1b  stloc.s  9
0x1ea1d  leave.s  loc_1EA51
0x1ea1f  ldarg.s  0xD
0x1ea21  brfalse.s loc_1EA2B
0x1ea23  ldarg.s  0xD
0x1ea25  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0x1ea2a  pop
0x1ea2b  ldloc.s  4
0x1ea2d  ldc.i4.1
0x1ea2e  add
0x1ea2f  stloc.s  4
0x1ea31  ldloc.s  4
0x1ea33  ldarg.0
0x1ea34  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1ea39  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1ea3e  blt      loc_1E8BA
0x1ea43  leave.s  loc_1EA4F
0x1ea45  ldloc.1
0x1ea46  brfalse.s loc_1EA4E
0x1ea48  ldloc.1
0x1ea49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ea4e  endfinally
0x1ea4f  ldnull
0x1ea50  ret
0x1ea51  ldloc.s  9
0x1ea53  ret
```
