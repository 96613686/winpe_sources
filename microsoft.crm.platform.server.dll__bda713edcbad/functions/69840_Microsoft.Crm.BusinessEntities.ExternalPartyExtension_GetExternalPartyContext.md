# Microsoft.Crm.BusinessEntities.ExternalPartyExtension::GetExternalPartyContext

- ea: `0x69840`
- end: `0x69aca`
- name: `Microsoft.Crm.BusinessEntities.ExternalPartyExtension::GetExternalPartyContext`
- size: `650`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x69680`

## callees

- `0x13b10`
- `0x18520`
- `0x18540`
- `0x18800`
- `0x193b0`
- `0x1ae30`
- `0x1b170`
- `0x1ef80`
- `0x1fc10`
- `0x240d0`
- `0x5d570`
- `0x66b00`
- `0x66b30`
- `0x66b60`
- `0x67cf0`
- `0x69840`

## string_xrefs

- `0x6992e`: `ChannelAccessProfile`
- `0x69873`: `channelaccessprofileid`
- `0x69933`: `channelaccessprofileid`
- `0x69938`: `channelaccessprofileid`

## pseudocode

```c

```

## disassembly

```asm
0x69840  ldloca.s 0
0x69842  initobj  LocalContextData
0x69848  ldloca.s 0
0x6984a  ldarg.1
0x6984b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerRegardingObject()
0x69850  stfld    valuetype [mscorlib]System.Guid LocalContextData::RegardingObjectId
0x69855  ldloca.s 0
0x69857  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6985c  stfld    valuetype [mscorlib]System.Guid LocalContextData::ProfileId
0x69861  ldstr    aExternalpartyi// "ExternalPartyItem"
0x69866  ldarg.1
0x69867  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x6986c  stloc.1
0x6986d  ldloc.1
0x6986e  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x69873  ldstr    aChannelaccessp_3// "channelaccessprofileid"
0x69878  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x6987d  ldloc.1
0x6987e  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x69883  ldstr    aRegardingobjec// "regardingobjecttypecode"
0x69888  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x6988d  ldloc.1
0x6988e  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x69893  ldstr    aRegardingobjec_1// "regardingobjectidname"
0x69898  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x6989d  ldloc.1
0x6989e  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x698a3  ldstr    aRegardingobjec_7// "regardingobjectidyominame"
0x698a8  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x698ad  ldloc.1
0x698ae  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x698b3  ldstr    aRegardingobjec_0// "regardingobjectid"
0x698b8  ldc.i4.0
0x698b9  ldarg.1
0x698ba  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerRegardingObject()
0x698bf  box      [mscorlib]System.Guid
0x698c4  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x698c9  pop
0x698ca  ldloc.1
0x698cb  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x698d0  ldstr    aExternalpartyi_0// "externalpartyid"
0x698d5  ldc.i4.0
0x698d6  ldarg.1
0x698d7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_ExternalPartyId()
0x698dc  box      [mscorlib]System.Guid
0x698e1  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x698e6  pop
0x698e7  ldloc.1
0x698e8  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x698ed  ldstr    aStatecode// "statecode"
0x698f2  ldc.i4.0
0x698f3  ldc.i4.0
0x698f4  box      [mscorlib]System.Int32
0x698f9  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x698fe  pop
0x698ff  ldloc.1
0x69900  ldstr    aExternalparty// "ExternalParty"
0x69905  ldstr    aExternalpartyi_0// "externalpartyid"
0x6990a  ldstr    aExternalpartyi_0// "externalpartyid"
0x6990f  ldc.i4.0
0x69910  ldc.i4.2
0x69911  callvirt instance class Microsoft.Crm.Query.LinkEntityExpression Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string entityName, string attributeFrom, string attributeTo, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator joinOperator)
0x69916  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.LinkEntityExpression::get_Criteria()
0x6991b  ldstr    aStatecode// "statecode"
0x69920  ldc.i4.0
0x69921  ldc.i4.0
0x69922  box      [mscorlib]System.Int32
0x69927  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x6992c  pop
0x6992d  ldloc.1
0x6992e  ldstr    aChannelaccessp_1// "ChannelAccessProfile"
0x69933  ldstr    aChannelaccessp_3// "channelaccessprofileid"
0x69938  ldstr    aChannelaccessp_3// "channelaccessprofileid"
0x6993d  ldc.i4.0
0x6993e  ldc.i4.2
0x6993f  callvirt instance class Microsoft.Crm.Query.LinkEntityExpression Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string entityName, string attributeFrom, string attributeTo, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator joinOperator)
0x69944  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.LinkEntityExpression::get_Criteria()
0x69949  ldstr    aStatecode// "statecode"
0x6994e  ldc.i4.0
0x6994f  ldc.i4.0
0x69950  box      [mscorlib]System.Int32
0x69955  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x6995a  pop
0x6995b  ldarg.1
0x6995c  ldc.i4.1
0x6995d  newobj   instance void Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext context, bool switchAuditingInfo)
0x69962  stloc.2
0x69963  ldarg.1
0x69964  ldc.i4.1
0x69965  newobj   instance void Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::.ctor(class Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget queryTarget)
0x6996a  ldloc.1
0x6996b  newobj   instance void Microsoft.Crm.Query.SelectPlan::.ctor(class Microsoft.Crm.Query.ICrmSqlSelectCommandStrategy strategy, class Microsoft.Crm.Query.EntityExpression entity)
0x69970  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x69975  stloc.3
0x69976  ldarg.1
0x69977  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x6997c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x69981  ldarg.1
0x69982  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x69987  ldloc.3
0x69988  ldarg.1
0x69989  call     class [System.Data]System.Data.IDataReader Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteQuery(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection dbConnection, class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6998e  stloc.s  4
0x69990  ldloc.s  4
0x69992  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x69997  brtrue.s loc_699D5
0x69999  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6999e  ldstr    aInvalidExterna// "Invalid ExternalParty Parameters: Calle"...
0x699a3  ldc.i4.2
0x699a4  newarr   [mscorlib]System.Object
0x699a9  dup
0x699aa  ldc.i4.0
0x699ab  ldarg.1
0x699ac  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_ExternalPartyId()
0x699b1  box      [mscorlib]System.Guid
0x699b6  stelem.ref
0x699b7  dup
0x699b8  ldc.i4.1
0x699b9  ldarg.1
0x699ba  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerRegardingObject()
0x699bf  box      [mscorlib]System.Guid
0x699c4  stelem.ref
0x699c5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x699ca  ldc.i4   0x8006110E
0x699cf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x699d4  throw
0x699d5  ldloca.s 0
0x699d7  ldloc.s  4
0x699d9  ldc.i4.0
0x699da  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x699df  unbox.any [mscorlib]System.Guid
0x699e4  stfld    valuetype [mscorlib]System.Guid LocalContextData::ProfileId
0x699e9  ldloca.s 0
0x699eb  ldarg.1
0x699ec  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x699f1  ldloc.s  4
0x699f3  ldc.i4.1
0x699f4  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x699f9  unbox.any [mscorlib]System.Int32
0x699fe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x69a03  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata LocalContextData::RegardingObjectMetadata
0x69a08  ldloca.s 0
0x69a0a  ldloc.s  4
0x69a0c  ldc.i4.2
0x69a0d  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x69a12  isinst   [mscorlib]System.String
0x69a17  stfld    string LocalContextData::RegardingObjectIdName
0x69a1c  ldloca.s 0
0x69a1e  ldloc.s  4
0x69a20  ldc.i4.3
0x69a21  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(int32)
0x69a26  isinst   [mscorlib]System.String
0x69a2b  stfld    string LocalContextData::RegardingObjectIdYomiName
0x69a30  ldloc.s  4
0x69a32  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x69a37  brfalse.s loc_69A92
0x69a39  ldnull
0x69a3a  ldarg.1
0x69a3b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x69a40  ldc.i4.s 0x1D
0x69a42  ldstr    aExceptionWhenE_4// "Exception when executing query: {0} Exc"...
0x69a47  ldc.i4.1
0x69a48  newarr   [mscorlib]System.Object
0x69a4d  dup
0x69a4e  ldc.i4.0
0x69a4f  ldloc.3
0x69a50  stelem.ref
0x69a51  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x69a56  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x69a5b  ldstr    aInvalidExterna// "Invalid ExternalParty Parameters: Calle"...
0x69a60  ldc.i4.2
0x69a61  newarr   [mscorlib]System.Object
0x69a66  dup
0x69a67  ldc.i4.0
0x69a68  ldarg.1
0x69a69  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_ExternalPartyId()
0x69a6e  box      [mscorlib]System.Guid
0x69a73  stelem.ref
0x69a74  dup
0x69a75  ldc.i4.1
0x69a76  ldarg.1
0x69a77  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerRegardingObject()
0x69a7c  box      [mscorlib]System.Guid
0x69a81  stelem.ref
0x69a82  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x69a87  ldc.i4   0x8006110F
0x69a8c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x69a91  throw
0x69a92  leave.s  loc_69AC8
0x69a94  ldloc.s  4
0x69a96  brfalse.s loc_69A9F
0x69a98  ldloc.s  4
0x69a9a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69a9f  endfinally
0x69aa0  ldarg.1
0x69aa1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x69aa6  brfalse.s loc_69AB3
0x69aa8  ldarg.1
0x69aa9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x69aae  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x69ab3  endfinally
0x69ab4  ldloc.3
0x69ab5  brfalse.s loc_69ABD
0x69ab7  ldloc.3
0x69ab8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69abd  endfinally
0x69abe  ldloc.2
0x69abf  brfalse.s loc_69AC7
0x69ac1  ldloc.2
0x69ac2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69ac7  endfinally
0x69ac8  ldloc.0
0x69ac9  ret
```
