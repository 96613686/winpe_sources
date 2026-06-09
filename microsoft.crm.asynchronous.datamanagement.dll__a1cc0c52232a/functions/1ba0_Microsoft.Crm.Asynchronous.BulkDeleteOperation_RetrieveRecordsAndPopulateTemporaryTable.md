# Microsoft.Crm.Asynchronous.BulkDeleteOperation::RetrieveRecordsAndPopulateTemporaryTable

- ea: `0x1ba0`
- end: `0x1da2`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::RetrieveRecordsAndPopulateTemporaryTable`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## callees

- `0x10d0`
- `0x1110`
- `0x1ba0`
- `0x1fb0`
- `0x2150`

## pseudocode

```c

```

## disassembly

```asm
0x1ba0  ldc.i4.0
0x1ba1  stloc.0
0x1ba2  br       loc_1D8D
0x1ba7  ldarg.0
0x1ba8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_globalQueryExpList
0x1bad  ldarg.3
0x1bae  ldloc.0
0x1baf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::get_Item(!!T0)
0x1bb4  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::IndexOf(var<u1>)
0x1bb9  stloc.1
0x1bba  ldc.i4.0
0x1bbb  stloc.2
0x1bbc  ldarg.3
0x1bbd  ldloc.0
0x1bbe  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::get_Item(!!T0)
0x1bc3  stloc.3
0x1bc4  ldarg.1
0x1bc5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1bca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1bcf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1bd4  ldloc.3
0x1bd5  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x1bda  ldc.i4.1
0x1bdb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1be0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x1be5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1bea  stloc.s  4
0x1bec  ldloc.3
0x1bed  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x1bf2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x1bf7  ldloc.3
0x1bf8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x1bfd  ldloc.s  4
0x1bff  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x1c04  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0x1c09  stloc.s  5
0x1c0b  ldnull
0x1c0c  stloc.s  6
0x1c0e  ldnull
0x1c0f  stloc.s  7
0x1c11  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::.ctor()
0x1c16  stloc.s  8
0x1c18  ldloc.s  8
0x1c1a  ldc.i4   0x3E8
0x1c1f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::set_Count(int32)
0x1c24  ldloc.s  8
0x1c26  ldloc.2
0x1c27  ldc.i4.1
0x1c28  add
0x1c29  dup
0x1c2a  stloc.2
0x1c2b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::set_PageNumber(int32)
0x1c30  ldloc.3
0x1c31  ldloc.s  8
0x1c33  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_PageInfo(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo)
0x1c38  ldloc.s  5
0x1c3a  ldloc.3
0x1c3b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x1c40  ldarg.0
0x1c41  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x1c46  ldloc.s  5
0x1c48  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x1c4d  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0x1c52  stloc.s  7
0x1c54  ldloc.s  7
0x1c56  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x1c5b  stloc.s  6
0x1c5d  ldloc.s  8
0x1c5f  ldloc.s  7
0x1c61  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x1c66  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_PagingCookie()
0x1c6b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.PagingInfo::set_PagingCookie(string)
0x1c70  ldloc.s  6
0x1c72  brfalse  loc_1D30
0x1c77  ldloc.s  6
0x1c79  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1c7e  brfalse  loc_1D30
0x1c83  ldloc.s  6
0x1c85  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1c8a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1c8f  brfalse  loc_1D30
0x1c94  ldc.i4.0
0x1c95  stloc.s  9
0x1c97  br.s     loc_1CD5
0x1c99  ldloc.s  6
0x1c9b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1ca0  ldloc.s  9
0x1ca2  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x1ca7  stloc.s  0xA
0x1ca9  ldarg.0
0x1caa  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1caf  ldarg.2
0x1cb0  ldloc.s  0xA
0x1cb2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x1cb7  ldloc.s  0xA
0x1cb9  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x1cbe  ldloc.1
0x1cbf  ldarg.1
0x1cc0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_CorrelationToken()
0x1cc5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::get_CorrelationId()
0x1cca  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::CreateTempTableRow(string tableName, valuetype [mscorlib]System.Guid recordId, string entityName, int32 queryIndex, valuetype [mscorlib]System.Guid correlationId)
0x1ccf  ldloc.s  9
0x1cd1  ldc.i4.1
0x1cd2  add
0x1cd3  stloc.s  9
0x1cd5  ldloc.s  9
0x1cd7  ldloc.s  6
0x1cd9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1cde  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1ce3  blt.s    loc_1C99
0x1ce5  ldloc.s  6
0x1ce7  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_MoreRecords()
0x1cec  brfalse.s loc_1D30
0x1cee  ldarg.1
0x1cef  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::QueryForEarlyExitRequest()
0x1cf4  stloc.s  0xB
0x1cf6  ldloc.s  0xB
0x1cf8  ldc.i4.1
0x1cf9  beq.s    loc_1D05
0x1cfb  ldloc.s  0xB
0x1cfd  ldc.i4.2
0x1cfe  beq.s    loc_1D1B
0x1d00  br       loc_1C24
0x1d05  ldarg.s  4
0x1d07  brfalse.s loc_1D0F
0x1d09  ldarg.0
0x1d0a  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperation::PauseAllChildJobs()
0x1d0f  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor()
0x1d14  stloc.s  0xC
0x1d16  leave    loc_1D9F
0x1d1b  ldarg.0
0x1d1c  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1d21  ldarg.2
0x1d22  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::DeleteTempTable(string tableName)
0x1d27  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor()
0x1d2c  stloc.s  0xC
0x1d2e  leave.s  loc_1D9F
0x1d30  leave.s  loc_1D89
0x1d32  stloc.s  0xD
0x1d34  ldloc.s  0xD
0x1d36  ldarg.0
0x1d37  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.BulkDeleteOperation::_organizationId
0x1d3c  ldc.i4.s 0x15
0x1d3e  ldstr    aErrorInRetriev// "Error In Retrieving data set for deleti"...
0x1d43  ldc.i4.1
0x1d44  newarr   [mscorlib]System.Object
0x1d49  dup
0x1d4a  ldc.i4.0
0x1d4b  ldloc.s  0xD
0x1d4d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x1d52  stelem.ref
0x1d53  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1d58  ldloc.s  0xD
0x1d5a  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1d5f  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x1d64  stloc.s  0xE
0x1d66  ldarg.0
0x1d67  ldarg.1
0x1d68  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d6d  ldloc.3
0x1d6e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x1d73  ldloc.1
0x1d74  ldloc.s  0xD
0x1d76  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x1d7b  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_Message()
0x1d80  ldloc.s  0xE
0x1d82  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperation::CreateFailureRow(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, valuetype [mscorlib]System.Guid recordId, string entityName, int32 queryIndex, string errorMessage, int32 crmErrorCode)
0x1d87  leave.s  loc_1D89
0x1d89  ldloc.0
0x1d8a  ldc.i4.1
0x1d8b  add
0x1d8c  stloc.0
0x1d8d  ldloc.0
0x1d8e  ldarg.3
0x1d8f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::get_Count()
0x1d94  blt      loc_1BA7
0x1d99  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x1d9e  ret
0x1d9f  ldloc.s  0xC
0x1da1  ret
```
