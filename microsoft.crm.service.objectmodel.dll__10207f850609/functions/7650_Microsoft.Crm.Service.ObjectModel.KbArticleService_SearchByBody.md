# Microsoft.Crm.Service.ObjectModel.KbArticleService::SearchByBody

- ea: `0x7650`
- end: `0x768c`
- name: `Microsoft.Crm.Service.ObjectModel.KbArticleService::SearchByBody`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x7640`

## callees

- `0x61a0`
- `0x61b0`
- `0x7690`
- `0x7720`

## pseudocode

```c

```

## disassembly

```asm
0x7650  ldarg.0
0x7651  ldarg.1
0x7652  call     instance void Microsoft.Crm.Service.ObjectModel.KbArticleService::ValidateSearchTextLength(string searchText)
0x7657  ldarg.s  4
0x7659  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x765e  ldc.i4.1
0x765f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_ReturnTotalRecordCount(bool)
0x7664  newobj   instance void Microsoft.Crm.Service.ObjectModel.DocumentIndexService::.ctor()
0x7669  ldarg.1
0x766a  ldarg.2
0x766b  ldarg.3
0x766c  ldstr    aDocumentindex// "DocumentIndex"
0x7671  ldarg.s  5
0x7673  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x7678  ldarg.s  5
0x767a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.DocumentIndexService::SearchByBody(string searchText, valuetype [mscorlib]System.Guid subjectId, bool useInflection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression columnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x767f  stloc.0
0x7680  ldarg.0
0x7681  ldloc.0
0x7682  ldarg.s  4
0x7684  ldarg.s  5
0x7686  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.KbArticleService::RetrieveKbArticlesByDocumentIndexes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection documentIndexEntities, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x768b  ret
```
