# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleViewsService::IncrementKnowledgeArticleViewCountId

- ea: `0x104e0`
- end: `0x1052f`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleViewsService::IncrementKnowledgeArticleViewCountId`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x10340`

## string_xrefs

- `0x104ed`: `knowledgearticleviewsid`
- `0x104f3`: `knowledgearticleviewsid`

## pseudocode

```c

```

## disassembly

```asm
0x104e0  ldarg.1
0x104e1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x104e6  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticleViews::.ctor(valuetype [mscorlib]System.Guid)
0x104eb  stloc.0
0x104ec  ldloc.0
0x104ed  ldstr    aKnowledgeartic_8// "knowledgearticleviewsid"
0x104f2  ldarg.2
0x104f3  ldstr    aKnowledgeartic_8// "knowledgearticleviewsid"
0x104f8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x104fd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x10502  ldarg.2
0x10503  ldstr    aKnowledgeartic_9// "knowledgearticleview"
0x10508  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1050d  unbox.any [mscorlib]System.Int32
0x10512  stloc.1
0x10513  ldloc.0
0x10514  ldstr    aKnowledgeartic_9// "knowledgearticleview"
0x10519  ldloc.1
0x1051a  ldarg.3
0x1051b  add
0x1051c  box      [mscorlib]System.Int32
0x10521  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x10526  ldarg.0
0x10527  ldloc.0
0x10528  ldarg.1
0x10529  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1052e  ret
```
