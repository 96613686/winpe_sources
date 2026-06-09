# Microsoft.Crm.ObjectModel.OrgInsights.EntityExpressionResolver::ResolveSavedOrgInsightsConfigurationEntityExpression

- ea: `0x200800`
- end: `0x20091d`
- name: `Microsoft.Crm.ObjectModel.OrgInsights.EntityExpressionResolver::ResolveSavedOrgInsightsConfigurationEntityExpression`
- size: `285`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7f9e0`
- `0x7fa60`

## callees

- `0x200120`
- `0x2003c0`
- `0x200520`
- `0x200800`
- `0x200c80`
- `0x201170`

## string_xrefs

- `0x200849`: `SavedOrgInsightsConfiguration`
- `0x200865`: `SavedOrgInsightsConfiguration`
- `0x200881`: `SavedOrgInsightsConfiguration`
- `0x200908`: `SavedOrgInsightsConfiguration`
- `0x200854`: `savedorginsightsconfigurationid`
- `0x200870`: `jsondatastarttime`
- `0x20088c`: `jsondataendtime`

## pseudocode

```c

```

## disassembly

```asm
0x200800  ldarg.0
0x200801  brfalse.s loc_20083C
0x200803  ldarg.0
0x200804  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x200809  brfalse.s loc_20083C
0x20080b  ldarg.0
0x20080c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x200811  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Conditions()
0x200816  brfalse.s loc_20083C
0x200818  ldarg.0
0x200819  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x20081e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Conditions()
0x200823  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>::get_Count()
0x200828  brtrue.s loc_200842
0x20082a  ldarg.0
0x20082b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x200830  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Filters()
0x200835  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression>::get_Count()
0x20083a  brtrue.s loc_200842
0x20083c  newobj   instance void Microsoft.Crm.ObjectModel.OrgInsights.ParseResult::.ctor()
0x200841  ret
0x200842  nop
0x200843  ldarg.1
0x200844  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x200849  ldstr    aSavedorginsigh// "SavedOrgInsightsConfiguration"
0x20084e  ldc.i4.0
0x20084f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x200854  ldstr    aSavedorginsigh_0// "savedorginsightsconfigurationid"
0x200859  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x20085e  stloc.0
0x20085f  ldarg.1
0x200860  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x200865  ldstr    aSavedorginsigh// "SavedOrgInsightsConfiguration"
0x20086a  ldc.i4.0
0x20086b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x200870  ldstr    aJsondatastartt// "jsondatastarttime"
0x200875  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x20087a  stloc.1
0x20087b  ldarg.1
0x20087c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x200881  ldstr    aSavedorginsigh// "SavedOrgInsightsConfiguration"
0x200886  ldc.i4.0
0x200887  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x20088c  ldstr    aJsondataendtim// "jsondataendtime"
0x200891  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x200896  stloc.2
0x200897  ldarg.0
0x200898  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x20089d  ldarg.1
0x20089e  ldloc.1
0x20089f  ldc.i4.0
0x2008a0  call     bool Microsoft.Crm.ObjectModel.OrgInsights.EntityExpressionResolver::ValidateSingleTimeFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression filterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata timeAttribute, bool isTimeFiltered)
0x2008a5  pop
0x2008a6  ldarg.0
0x2008a7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2008ac  ldarg.1
0x2008ad  ldloc.2
0x2008ae  ldc.i4.0
0x2008af  call     bool Microsoft.Crm.ObjectModel.OrgInsights.EntityExpressionResolver::ValidateSingleTimeFilter(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression filterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata timeAttribute, bool isTimeFiltered)
0x2008b4  pop
0x2008b5  newobj   instance void Microsoft.Crm.ObjectModel.OrgInsights.ParseResult::.ctor()
0x2008ba  stloc.3
0x2008bb  ldarg.0
0x2008bc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2008c1  ldarg.1
0x2008c2  ldloc.0
0x2008c3  ldloc.1
0x2008c4  ldloc.2
0x2008c5  ldloc.3
0x2008c6  call     valuetype Microsoft.Crm.ObjectModel.OrgInsights.FilterType Microsoft.Crm.ObjectModel.OrgInsights.EntityExpressionResolver::EvaluateFilterSetExpression(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression filterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata primaryKeyAttribute, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata startTimeAttribute, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata endTimeAttribute, class Microsoft.Crm.ObjectModel.OrgInsights.ParseResult entityExpressionResult)
0x2008cb  pop
0x2008cc  ldloc.3
0x2008cd  ldloc.3
0x2008ce  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.OrgInsights.ParseResult::IdFilter
0x2008d3  brtrue.s loc_2008D8
0x2008d5  ldnull
0x2008d6  br.s     loc_2008E8
0x2008d8  ldloc.3
0x2008d9  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.OrgInsights.ParseResult::IdFilter
0x2008de  call     T0x2B000248
0x2008e3  call     T0x2B000039
0x2008e8  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.OrgInsights.ParseResult::IdFilter
0x2008ed  ldloc.3
0x2008ee  stloc.s  4
0x2008f0  leave.s  loc_20091A
0x2008f2  pop
0x2008f3  call     class Microsoft.Crm.ObjectModel.OrgInsights.OrgInsightsTelemetryEvents Microsoft.Crm.ObjectModel.OrgInsights.OrgInsightsTelemetryEvents::get_Instance()
0x2008f8  ldarg.1
0x2008f9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2008fe  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x200903  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserPuid()
0x200908  ldstr    aSavedorginsigh// "SavedOrgInsightsConfiguration"
0x20090d  ldarg.0
0x20090e  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::SerializeToFetchXml()
0x200913  callvirt instance void Microsoft.Crm.ObjectModel.OrgInsights.OrgInsightsTelemetryEvents::ExpressionNotSupported(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string userPuid, string entityName, string fetchXml)
0x200918  rethrow
0x20091a  ldloc.s  4
0x20091c  ret
```
