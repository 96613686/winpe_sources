# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CheckKnowledgeArticlePermission

- ea: `0xf550`
- end: `0xf59a`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CheckKnowledgeArticlePermission`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xd3e0`
- `0xd4b0`

## callees

- `0xf550`
- `0xf600`
- `0xf730`

## pseudocode

```c

```

## disassembly

```asm
0xf550  ldarg.0
0xf551  ldarg.1
0xf552  ldc.i4.1
0xf553  newarr   [mscorlib]System.String
0xf558  dup
0xf559  ldc.i4.0
0xf55a  ldstr    aStatecode// "statecode"
0xf55f  stelem.ref
0xf560  ldarg.2
0xf561  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetrieveKnowledgeArticle(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, string[] columnSet, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf566  stloc.0
0xf567  ldloc.0
0xf568  ldstr    aStatecode// "statecode"
0xf56d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xf572  brfalse.s loc_F599
0xf574  ldloc.0
0xf575  ldstr    aStatecode// "statecode"
0xf57a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xf57f  unbox.any [mscorlib]System.Int32
0xf584  stloc.1
0xf585  ldloc.1
0xf586  ldc.i4.2
0xf587  beq.s    loc_F58D
0xf589  ldloc.1
0xf58a  ldc.i4.3
0xf58b  bne.un.s loc_F599
0xf58d  ldarg.0
0xf58e  ldstr    aPrvpublishknow// "prvPublishKnowledgeArticle"
0xf593  ldarg.2
0xf594  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CheckKnowledgeArticlePermission(string privilege, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf599  ret
```
