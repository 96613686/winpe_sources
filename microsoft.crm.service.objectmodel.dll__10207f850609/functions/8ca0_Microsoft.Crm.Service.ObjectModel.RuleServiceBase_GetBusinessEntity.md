# Microsoft.Crm.Service.ObjectModel.RuleServiceBase::GetBusinessEntity

- ea: `0x8ca0`
- end: `0x8dad`
- name: `Microsoft.Crm.Service.ObjectModel.RuleServiceBase::GetBusinessEntity`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x8c40`
- `0x90d0`

## callees

- `0x89f0`
- `0x8a00`
- `0x8a10`
- `0x8ca0`

## pseudocode

```c

```

## disassembly

```asm
0x8ca0  ldarg.0
0x8ca1  callvirt instance string Microsoft.Crm.Service.ObjectModel.RuleServiceBase::get_EntityName()
0x8ca6  ldarg.2
0x8ca7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x8cac  stloc.0
0x8cad  ldloc.0
0x8cae  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x8cb3  ldc.i4.1
0x8cb4  newarr   [mscorlib]System.String
0x8cb9  dup
0x8cba  ldc.i4.0
0x8cbb  ldstr    aWorkflowid// "workflowid"
0x8cc0  stelem.ref
0x8cc1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x8cc6  ldloc.0
0x8cc7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x8ccc  ldc.i4.1
0x8ccd  newarr   [mscorlib]System.String
0x8cd2  dup
0x8cd3  ldc.i4.0
0x8cd4  ldstr    aOwnerid// "ownerid"
0x8cd9  stelem.ref
0x8cda  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x8cdf  ldloc.0
0x8ce0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x8ce5  ldarg.0
0x8ce6  callvirt instance string[] Microsoft.Crm.Service.ObjectModel.RuleServiceBase::GetColumnsToUpdate()
0x8ceb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x8cf0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x8cf5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x8cfa  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0x8cff  ldarg.2
0x8d00  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8d05  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x8d0a  ldarg.2
0x8d0b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8d10  ldarg.2
0x8d11  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x8d16  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x8d1b  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x8d20  brfalse.s loc_8D5A
0x8d22  ldarg.1
0x8d23  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x8d28  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8d2d  ldstr    aConvertrule// "ConvertRule"
0x8d32  callvirt instance bool [mscorlib]System.String::Equals(string)
0x8d37  brfalse.s loc_8D5A
0x8d39  ldloc.0
0x8d3a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x8d3f  ldc.i4.2
0x8d40  newarr   [mscorlib]System.String
0x8d45  dup
0x8d46  ldc.i4.0
0x8d47  ldstr    aSourcechannelt// "sourcechanneltypecode"
0x8d4c  stelem.ref
0x8d4d  dup
0x8d4e  ldc.i4.1
0x8d4f  ldstr    aChannelpropert// "channelpropertygroupid"
0x8d54  stelem.ref
0x8d55  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x8d5a  ldloc.0
0x8d5b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x8d60  ldarg.0
0x8d61  callvirt instance string Microsoft.Crm.Service.ObjectModel.RuleServiceBase::get_PrimaryColumnName()
0x8d66  ldc.i4.0
0x8d67  ldarg.1
0x8d68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x8d6d  box      [mscorlib]System.Guid
0x8d72  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x8d77  pop
0x8d78  ldarg.2
0x8d79  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8d7e  stloc.1
0x8d7f  ldarg.0
0x8d80  ldarg.1
0x8d81  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x8d86  ldarg.1
0x8d87  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x8d8c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8d91  ldarg.2
0x8d92  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8d97  ldloc.0
0x8d98  ldarg.2
0x8d99  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8d9e  stloc.2
0x8d9f  leave.s  loc_8DAB
0x8da1  ldloc.1
0x8da2  brfalse.s loc_8DAA
0x8da4  ldloc.1
0x8da5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8daa  endfinally
0x8dab  ldloc.2
0x8dac  ret
```
