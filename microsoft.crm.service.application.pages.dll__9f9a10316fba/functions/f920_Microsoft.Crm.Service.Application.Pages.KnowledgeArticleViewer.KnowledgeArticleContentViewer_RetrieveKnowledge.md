# Microsoft.Crm.Service.Application.Pages.KnowledgeArticleViewer.KnowledgeArticleContentViewer::RetrieveKnowledgeArticleContent

- ea: `0xf920`
- end: `0xf99c`
- name: `Microsoft.Crm.Service.Application.Pages.KnowledgeArticleViewer.KnowledgeArticleContentViewer::RetrieveKnowledgeArticleContent`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xf8c0`

## callees

- `0xf920`
- `0xf9a0`

## pseudocode

```c

```

## disassembly

```asm
0xf920  ldsfld   string [mscorlib]System.String::Empty
0xf925  stloc.0
0xf926  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor()
0xf92b  stloc.1
0xf92c  ldloc.1
0xf92d  ldstr    aContent// "content"
0xf932  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0xf937  ldstr    aKnowledgeartic_0// "knowledgearticle"
0xf93c  ldarg.1
0xf93d  ldloc.1
0xf93e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf943  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf948  ldstr    aContent// "content"
0xf94d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xf952  isinst   [mscorlib]System.String
0xf957  stloc.0
0xf958  ldloc.0
0xf959  stloc.2
0xf95a  leave.s  loc_F99A
0xf95c  stloc.3
0xf95d  ldloc.3
0xf95e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf963  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xf968  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0xf96d  ldstr    aKnowledgeartic_1// "/KnowledgeArticleContentViewer/Knowledg"...
0xf972  ldc.i4.2
0xf973  newarr   [mscorlib]System.Object
0xf978  dup
0xf979  ldc.i4.0
0xf97a  ldarg.1
0xf97b  box      [mscorlib]System.Guid
0xf980  stelem.ref
0xf981  dup
0xf982  ldc.i4.1
0xf983  ldloc.3
0xf984  callvirt instance string [mscorlib]System.Object::ToString()
0xf989  stelem.ref
0xf98a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf98f  ldarg.0
0xf990  ldloc.3
0xf991  call     instance void Microsoft.Crm.Service.Application.Pages.KnowledgeArticleViewer.KnowledgeArticleContentViewer::ShowErrorMessage(class [Microsoft.Crm.Core]Microsoft.Crm.CrmException crmException)
0xf996  leave.s  loc_F998
0xf998  ldloc.0
0xf999  ret
0xf99a  ldloc.2
0xf99b  ret
```
