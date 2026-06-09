# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::FullTextSearchKnowledgeArticle

- ea: `0xcbe0`
- end: `0xccae`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::FullTextSearchKnowledgeArticle`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x61a0`
- `0x61d0`
- `0xe500`
- `0xe9c0`
- `0x10130`
- `0x10140`

## pseudocode

```c

```

## disassembly

```asm
0xcbe0  ldarg.1
0xcbe1  ldstr    aSearchtext_0// "searchText"
0xcbe6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xcbeb  ldarg.s  5
0xcbed  ldstr    aEntityexpressi// "entityExpression"
0xcbf2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xcbf7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xcbfc  stloc.s  5
0xcbfe  ldloca.s 5
0xcc00  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xcc05  stloc.0
0xcc06  ldarg.0
0xcc07  ldarg.1
0xcc08  ldarg.s  6
0xcc0a  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::ValidateSearchTextLength(string searchText, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xcc0f  ldarg.s  5
0xcc11  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0xcc16  ldc.i4.1
0xcc17  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_ReturnTotalRecordCount(bool)
0xcc1c  newobj   instance void Microsoft.Crm.Service.ObjectModel.DocumentIndexService::.ctor()
0xcc21  ldarg.1
0xcc22  ldarg.s  4
0xcc24  ldarg.3
0xcc25  ldarg.2
0xcc26  ldstr    aDocumentindex// "DocumentIndex"
0xcc2b  ldarg.s  6
0xcc2d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xcc32  ldarg.s  6
0xcc34  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.DocumentIndexService::FullTextSearchByBody(string searchText, int32 stateCode, bool removeDuplicates, bool useInflection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression columnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xcc39  stloc.1
0xcc3a  ldarg.s  6
0xcc3c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xcc41  ldc.i4.s 0x1A
0xcc43  ldstr    a0// "{0}"
0xcc48  ldc.i4.1
0xcc49  newarr   [mscorlib]System.Object
0xcc4e  dup
0xcc4f  ldc.i4.0
0xcc50  ldstr    aDocumentIndexe// "Document Indexes retrieved based on sea"...
0xcc55  stelem.ref
0xcc56  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcc5b  ldarg.0
0xcc5c  ldloc.1
0xcc5d  ldarg.3
0xcc5e  ldarg.s  4
0xcc60  ldarg.s  5
0xcc62  ldarg.s  6
0xcc64  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetrieveKbArticlesByDocumentIndexes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection documentIndexEntities, bool removeDuplicates, int32 stateCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xcc69  stloc.2
0xcc6a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xcc6f  stloc.s  5
0xcc71  ldloca.s 5
0xcc73  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0xcc78  stloc.3
0xcc79  ldloca.s 4
0xcc7b  ldloc.3
0xcc7c  ldloc.0
0xcc7d  sub
0xcc7e  call     instance void [mscorlib]System.TimeSpan::.ctor(int64)
0xcc83  call     class Microsoft.Crm.Service.ObjectModel.KnowledgeArticleTelemetryEvents Microsoft.Crm.Service.ObjectModel.KnowledgeArticleTelemetryEvents::get_Instance()
0xcc88  ldarg.s  6
0xcc8a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xcc8f  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0xcc94  ldloca.s 4
0xcc96  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0xcc9b  ldarg.1
0xcc9c  callvirt instance int32 [mscorlib]System.String::get_Length()
0xcca1  ldloc.2
0xcca2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_TotalRecordCount()
0xcca7  callvirt instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleTelemetryEvents::LogSearchStats(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, float64 searchTime, int32 lengthOfSearchText, int32 searchResultCount)
0xccac  ldloc.2
0xccad  ret
```
