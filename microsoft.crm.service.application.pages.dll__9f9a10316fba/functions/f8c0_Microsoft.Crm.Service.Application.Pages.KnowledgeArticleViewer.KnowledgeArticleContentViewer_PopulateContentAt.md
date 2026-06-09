# Microsoft.Crm.Service.Application.Pages.KnowledgeArticleViewer.KnowledgeArticleContentViewer::PopulateContentAttribute

- ea: `0xf8c0`
- end: `0xf917`
- name: `Microsoft.Crm.Service.Application.Pages.KnowledgeArticleViewer.KnowledgeArticleContentViewer::PopulateContentAttribute`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xf8a0`

## callees

- `0xf8c0`
- `0xf920`

## pseudocode

```c

```

## disassembly

```asm
0xf8c0  ldarg.0
0xf8c1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf8c6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf8cb  ldstr    aId// "id"
0xf8d0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf8d5  stloc.0
0xf8d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf8db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xf8e0  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0xf8e5  ldstr    aKnowledgeartic// "/KnowledgeArticleContentViewer/Knowledg"...
0xf8ea  ldc.i4.1
0xf8eb  newarr   [mscorlib]System.Object
0xf8f0  dup
0xf8f1  ldc.i4.0
0xf8f2  ldloc.0
0xf8f3  stelem.ref
0xf8f4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf8f9  ldloc.0
0xf8fa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf8ff  brtrue.s loc_F916
0xf901  ldloca.s 1
0xf903  ldloc.0
0xf904  call     instance void [mscorlib]System.Guid::.ctor(string)
0xf909  ldarg.0
0xf90a  ldarg.0
0xf90b  ldloc.1
0xf90c  call     instance string Microsoft.Crm.Service.Application.Pages.KnowledgeArticleViewer.KnowledgeArticleContentViewer::RetrieveKnowledgeArticleContent(valuetype [mscorlib]System.Guid knowledgeArticleUniqueId)
0xf911  stfld    string Microsoft.Crm.Service.Application.Pages.KnowledgeArticleViewer.KnowledgeArticleContentViewer::_content
0xf916  ret
```
