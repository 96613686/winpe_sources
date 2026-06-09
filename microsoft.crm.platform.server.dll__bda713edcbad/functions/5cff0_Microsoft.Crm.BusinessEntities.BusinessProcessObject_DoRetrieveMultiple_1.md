# Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoRetrieveMultiple_1

- ea: `0x5cff0`
- end: `0x5d20a`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoRetrieveMultiple_1`
- size: `538`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x5cf40`
- `0x8cc60`

## callees

- `0x184b0`
- `0x184e0`
- `0x187b0`
- `0x1d320`
- `0x1d340`
- `0x1d360`
- `0x1ef80`
- `0x1fc10`
- `0x1fc70`
- `0x51950`
- `0x51b00`
- `0x58ef0`
- `0x59260`
- `0x5b500`
- `0x5c1a0`
- `0x5cff0`
- `0x5d210`
- `0x5d770`
- `0x5d7c0`
- `0x5e350`
- `0x5e360`
- `0x66a50`
- `0x66b00`
- `0x66ff0`

## string_xrefs

- `0x5cfff`: `securityQueryDetails`
- `0x5d012`: `securityQueryDetails`

## pseudocode

```c

```

## disassembly

```asm
0x5cff0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x5cff5  stloc.0
0x5cff6  ldnull
0x5cff7  stloc.1
0x5cff8  ldarg.s  5
0x5cffa  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5cfff  ldstr    aSecurityqueryd// "securityQueryDetails"
0x5d004  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5d009  brfalse.s loc_5D022
0x5d00b  ldarg.s  5
0x5d00d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5d012  ldstr    aSecurityqueryd// "securityQueryDetails"
0x5d017  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5d01c  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>
0x5d021  stloc.1
0x5d022  ldc.i4.1
0x5d023  ldarg.s  5
0x5d025  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5d02a  ldarg.1
0x5d02b  brfalse.s loc_5D035
0x5d02d  ldarg.1
0x5d02e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_EntityMetadata()
0x5d033  br.s     loc_5D036
0x5d035  ldnull
0x5d036  ldstr    aDoretrievemult_0// "DoRetrieveMultiple"
0x5d03b  ldarg.2
0x5d03c  callvirt instance bool Microsoft.Crm.Query.EntityExpression::get_IsLeadingWildCardQuery()
0x5d041  ldloc.1
0x5d042  call     void Microsoft.Crm.BusinessEntities.BusinessProcessObject::CaptureQueryDetailsUsingEntityMetadata(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.DataPerformance.InitiatorType initiator, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, string operationName, [opt] bool isLeadingWildCardQuery, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> securityQueryDetails)
0x5d047  ldnull
0x5d048  stloc.2
0x5d049  ldarg.s  5
0x5d04b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x5d050  stloc.2
0x5d051  ldloc.2
0x5d052  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x5d057  ldarg.0
0x5d058  ldarg.s  5
0x5d05a  ldarg.3
0x5d05b  callvirt instance class Microsoft.Crm.Query.ICrmSqlSelectCommandStrategy Microsoft.Crm.BusinessEntities.BusinessProcessObject::GetSelectCommandStrategy(class Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget queryTarget)
0x5d060  ldarg.2
0x5d061  newobj   instance void Microsoft.Crm.Query.SelectPlan::.ctor(class Microsoft.Crm.Query.ICrmSqlSelectCommandStrategy strategy, class Microsoft.Crm.Query.EntityExpression entity)
0x5d066  stloc.3
0x5d067  ldloc.3
0x5d068  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x5d06d  stloc.s  5
0x5d06f  ldstr    aExtendedretrie// "ExtendedRetrieveMultipleNullChecks"
0x5d074  ldc.i4.0
0x5d075  box      [mscorlib]System.Int32
0x5d07a  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x5d07f  unbox.any [mscorlib]System.Int32
0x5d084  ldc.i4.1
0x5d085  bne.un.s loc_5D0A6
0x5d087  ldnull
0x5d088  ldstr    aNotAnErrorExte_2// "Not An Error: [ExtendedRetrieveMultiple"...
0x5d08d  ldc.i4.1
0x5d08e  newarr   [mscorlib]System.Object
0x5d093  dup
0x5d094  ldc.i4.0
0x5d095  ldloc.3
0x5d096  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x5d09b  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x5d0a0  stelem.ref
0x5d0a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x5d0a6  ldloc.s  5
0x5d0a8  call     void Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetExtendedCommandTimeoutForRetrieveMultiple(class [System.Data]System.Data.IDbCommand sqlQuery)
0x5d0ad  ldarg.0
0x5d0ae  ldloc.2
0x5d0af  ldloc.s  5
0x5d0b1  ldarg.1
0x5d0b2  ldarg.2
0x5d0b3  ldarg.s  4
0x5d0b5  ldc.i4.1
0x5d0b6  ldloc.3
0x5d0b7  callvirt instance string Microsoft.Crm.Query.SelectPlan::get_AggregateLimitExceededName()
0x5d0bc  ldarg.s  5
0x5d0be  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::QueryAndFillEntityCollection(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class [System.Data]System.Data.IDbCommand dbCommand, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection entities, class Microsoft.Crm.Query.EntityExpression entityExp, class Microsoft.Crm.BusinessEntities.PagingHelper pagingHelper, bool useEntityExpression, string aggregateLimitExceededName, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5d0c3  ldarg.1
0x5d0c4  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5d0c9  stloc.s  6
0x5d0cb  br.s     loc_5D0F8
0x5d0cd  ldloc.s  6
0x5d0cf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5d0d4  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5d0d9  stloc.s  7
0x5d0db  ldarg.0
0x5d0dc  ldarg.2
0x5d0dd  ldloc.s  7
0x5d0df  ldarg.s  5
0x5d0e1  callvirt instance class Microsoft.Crm.Platform.Server.LocalizedEnumLabelCache Microsoft.Crm.BusinessEntities.ExecutionContext::get_LocalizedEnumLabelCache()
0x5d0e6  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetChildEnumAttributesOnBusinessEntity(class Microsoft.Crm.Query.EntityExpression entityExp, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class Microsoft.Crm.Platform.Server.LocalizedEnumLabelCache localizedEnumLabelCache)
0x5d0eb  ldarg.s  6
0x5d0ed  brfalse.s loc_5D0F8
0x5d0ef  ldarg.s  7
0x5d0f1  ldloc.s  7
0x5d0f3  call     void Microsoft.Crm.BusinessEntities.BusinessProcessObject::SetRowVersionAndClearVersionNumberIfRequired(bool isVersionNumberRequestedInRetrieve, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity)
0x5d0f8  ldloc.s  6
0x5d0fa  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5d0ff  brtrue.s loc_5D0CD
0x5d101  leave.s  loc_5D118
0x5d103  ldloc.s  6
0x5d105  isinst   [mscorlib]System.IDisposable
0x5d10a  stloc.s  8
0x5d10c  ldloc.s  8
0x5d10e  brfalse.s loc_5D117
0x5d110  ldloc.s  8
0x5d112  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d117  endfinally
0x5d118  leave.s  loc_5D14F
0x5d11a  stloc.s  9
0x5d11c  ldloc.s  9
0x5d11e  ldarg.s  5
0x5d120  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5d125  ldc.i4.s 0x1D
0x5d127  ldstr    aExceptionWhenE// "Exception when executing query: {0} Exc"...
0x5d12c  ldc.i4.2
0x5d12d  newarr   [mscorlib]System.Object
0x5d132  dup
0x5d133  ldc.i4.0
0x5d134  ldloc.s  5
0x5d136  stelem.ref
0x5d137  dup
0x5d138  ldc.i4.1
0x5d139  ldloc.s  9
0x5d13b  stelem.ref
0x5d13c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5d141  rethrow
0x5d143  ldloc.s  5
0x5d145  brfalse.s loc_5D14E
0x5d147  ldloc.s  5
0x5d149  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d14e  endfinally
0x5d14f  ldc.i4.m1
0x5d150  stloc.s  4
0x5d152  ldarg.2
0x5d153  callvirt instance class Microsoft.Crm.Query.PagingInfo Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x5d158  callvirt instance bool Microsoft.Crm.Query.PagingInfo::get_ReturnTotalRecordCount()
0x5d15d  brfalse.s loc_5D1B3
0x5d15f  ldarg.2
0x5d160  callvirt instance class Microsoft.Crm.Query.PagingInfo Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x5d165  callvirt instance int32 Microsoft.Crm.Query.PagingInfo::get_Count()
0x5d16a  brfalse.s loc_5D197
0x5d16c  ldarg.2
0x5d16d  callvirt instance class Microsoft.Crm.Query.PagingInfo Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x5d172  callvirt instance int32 Microsoft.Crm.Query.PagingInfo::get_PageNumber()
0x5d177  ldc.i4.1
0x5d178  bne.un.s loc_5D197
0x5d17a  ldarg.1
0x5d17b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_MoreRecords()
0x5d180  brtrue.s loc_5D197
0x5d182  ldarg.1
0x5d183  ldc.i4.0
0x5d184  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::set_TotalRecordCountLimitExceeded(bool)
0x5d189  ldarg.1
0x5d18a  ldarg.1
0x5d18b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5d190  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::set_TotalRecordCount(int32)
0x5d195  leave.s  loc_5D1BF
0x5d197  ldarg.1
0x5d198  ldarg.2
0x5d199  ldarg.s  5
0x5d19b  ldc.i4.1
0x5d19c  ldloca.s 4
0x5d19e  call     bool Microsoft.Crm.BusinessEntities.BusinessProcessObject::TryRetrieveExactTotalRecordCountForQuery(class Microsoft.Crm.Query.EntityExpression query, class Microsoft.Crm.BusinessEntities.ExecutionContext context, bool setExtendedTimeout, [out] int32& totalRecordCount)
0x5d1a3  ldc.i4.0
0x5d1a4  ceq
0x5d1a6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::set_TotalRecordCountLimitExceeded(bool)
0x5d1ab  ldarg.1
0x5d1ac  ldloc.s  4
0x5d1ae  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::set_TotalRecordCount(int32)
0x5d1b3  leave.s  loc_5D1BF
0x5d1b5  ldloc.2
0x5d1b6  brfalse.s loc_5D1BE
0x5d1b8  ldloc.2
0x5d1b9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x5d1be  endfinally
0x5d1bf  ldloc.0
0x5d1c0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x5d1c5  pop
0x5d1c6  call     class Microsoft.Crm.Platform.Server.BPOCrmTelemetryEvents Microsoft.Crm.Platform.Server.BPOCrmTelemetryEvents::get_Instance()
0x5d1cb  ldarg.s  5
0x5d1cd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5d1d2  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x5d1d7  ldarg.2
0x5d1d8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.EntityExpression::get_Entity()
0x5d1dd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5d1e2  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x5d1e7  ldloc.0
0x5d1e8  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x5d1ed  ldarg.2
0x5d1ee  call     string Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_CurrentClientId()
0x5d1f3  call     string Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_CurrentClientType()
0x5d1f8  ldarg.1
0x5d1f9  brtrue.s loc_5D1FE
0x5d1fb  ldc.i4.m1
0x5d1fc  br.s     loc_5D204
0x5d1fe  ldarg.1
0x5d1ff  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5d204  callvirt instance void Microsoft.Crm.Platform.Server.BPOCrmTelemetryEvents::BPOMultipleRetrieveCompleted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string entityName, string userPuid, int64 executionTime, class Microsoft.Crm.Query.EntityExpression entityExpression, string clientSessionId, string clientType, int32 numberOfRecords)
0x5d209  ret
```
