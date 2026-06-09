# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::Delete

- ea: `0xd4b0`
- end: `0xd6e8`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::Delete`
- size: `568`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0xd4b0`
- `0xf020`
- `0xf120`
- `0xf270`
- `0xf550`
- `0xf7b0`

## pseudocode

```c

```

## disassembly

```asm
0xd4b0  ldarg.0
0xd4b1  ldarg.1
0xd4b2  ldarg.2
0xd4b3  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CheckKnowledgeArticlePermission(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd4b8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd4bd  stloc.0
0xd4be  ldc.i4.6
0xd4bf  newarr   [mscorlib]System.String
0xd4c4  dup
0xd4c5  ldc.i4.0
0xd4c6  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xd4cb  stelem.ref
0xd4cc  dup
0xd4cd  ldc.i4.1
0xd4ce  ldstr    aIsrootarticle// "isrootarticle"
0xd4d3  stelem.ref
0xd4d4  dup
0xd4d5  ldc.i4.2
0xd4d6  ldstr    aArticlepublicn// "articlepublicnumber"
0xd4db  stelem.ref
0xd4dc  dup
0xd4dd  ldc.i4.3
0xd4de  ldstr    aRootarticleid// "rootarticleid"
0xd4e3  stelem.ref
0xd4e4  dup
0xd4e5  ldc.i4.4
0xd4e6  ldstr    aLanguagelocale// "languagelocaleid"
0xd4eb  stelem.ref
0xd4ec  dup
0xd4ed  ldc.i4.5
0xd4ee  ldstr    aIslatestversio// "islatestversion"
0xd4f3  stelem.ref
0xd4f4  stloc.1
0xd4f5  ldarg.0
0xd4f6  ldarg.1
0xd4f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd4fc  ldarg.2
0xd4fd  ldloc.1
0xd4fe  call     instance class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticle Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetrieveKnowledgeArticleById(valuetype [mscorlib]System.Guid knowledgeArticleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string[] columns)
0xd503  stloc.2
0xd504  ldloc.2
0xd505  ldstr    aArticlepublicn// "articlepublicnumber"
0xd50a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd50f  castclass [mscorlib]System.String
0xd514  stloc.3
0xd515  ldloc.2
0xd516  ldstr    aIsrootarticle// "isrootarticle"
0xd51b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xd520  brtrue.s loc_D593
0xd522  ldloc.2
0xd523  ldstr    aIsrootarticle// "isrootarticle"
0xd528  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd52d  unbox.any [mscorlib]System.Boolean
0xd532  brtrue.s loc_D593
0xd534  ldarg.0
0xd535  ldarg.1
0xd536  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd53b  ldloc.3
0xd53c  ldarg.2
0xd53d  call     instance bool Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::IsLastKnowledgeArticleVersion(valuetype [mscorlib]System.Guid knowledgeArticleID, string publicNumber, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd542  brfalse.s loc_D593
0xd544  ldloc.2
0xd545  ldstr    aRootarticleid// "rootarticleid"
0xd54a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xd54f  brtrue.s loc_D593
0xd551  ldarg.2
0xd552  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd557  ldc.i4.s 0x1A
0xd559  ldstr    a0// "{0}"
0xd55e  ldc.i4.1
0xd55f  newarr   [mscorlib]System.Object
0xd564  dup
0xd565  ldc.i4.0
0xd566  ldstr    aDeletingKnowle// "Deleting KnowledgeArticle={0} the last "...
0xd56b  ldarg.1
0xd56c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd571  box      [mscorlib]System.Guid
0xd576  ldloc.3
0xd577  call     string [mscorlib]System.String::Format(string, object, object)
0xd57c  stelem.ref
0xd57d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd582  ldloc.2
0xd583  ldstr    aRootarticleid// "rootarticleid"
0xd588  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd58d  unbox.any [mscorlib]System.Guid
0xd592  stloc.0
0xd593  ldarg.2
0xd594  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0xd599  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0xd59e  ldarg.2
0xd59f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd5a4  ldc.i4.s 0x1A
0xd5a6  ldstr    a0// "{0}"
0xd5ab  ldc.i4.1
0xd5ac  newarr   [mscorlib]System.Object
0xd5b1  dup
0xd5b2  ldc.i4.0
0xd5b3  ldstr    aClearningSelfR// " Clearning self references made on Know"...
0xd5b8  ldarg.1
0xd5b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd5be  box      [mscorlib]System.Guid
0xd5c3  call     string [mscorlib]System.String::Format(string, object)
0xd5c8  stelem.ref
0xd5c9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd5ce  ldarg.0
0xd5cf  ldarg.1
0xd5d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd5d5  ldarg.2
0xd5d6  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::ClearKnowledgeArticleSelfTableReferences(valuetype [mscorlib]System.Guid knowledgeArticleID, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd5db  ldarg.2
0xd5dc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0xd5e1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0xd5e6  ldarg.0
0xd5e7  ldarg.1
0xd5e8  ldarg.2
0xd5e9  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd5ee  ldloc.0
0xd5ef  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd5f4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xd5f9  brfalse.s loc_D643
0xd5fb  ldarg.2
0xd5fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd601  ldc.i4.s 0x1A
0xd603  ldstr    a0// "{0}"
0xd608  ldc.i4.1
0xd609  newarr   [mscorlib]System.Object
0xd60e  dup
0xd60f  ldc.i4.0
0xd610  ldstr    aDeletingRootar// "Deleting RootArticleId={0} on deletion "...
0xd615  ldloc.0
0xd616  box      [mscorlib]System.Guid
0xd61b  call     string [mscorlib]System.String::Format(string, object)
0xd620  stelem.ref
0xd621  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd626  ldloc.0
0xd627  ldstr    aKnowledgeartic// "KnowledgeArticle"
0xd62c  ldarg.2
0xd62d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd632  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0xd637  stloc.s  4
0xd639  ldarg.0
0xd63a  ldloc.s  4
0xd63c  ldarg.2
0xd63d  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd642  ret
0xd643  ldloc.2
0xd644  ldstr    aIslatestversio// "islatestversion"
0xd649  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd64e  unbox.any [mscorlib]System.Boolean
0xd653  brfalse  loc_D6E7
0xd658  ldarg.0
0xd659  ldloc.3
0xd65a  ldloc.2
0xd65b  ldstr    aLanguagelocale// "languagelocaleid"
0xd660  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd665  unbox.any [mscorlib]System.Guid
0xd66a  ldarg.2
0xd66b  call     instance class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32> Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::FindMaxVersionOfKnowledgeArticle(string publicNumber, valuetype [mscorlib]System.Guid languageLocaleID, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd670  stloc.s  5
0xd672  ldloc.s  5
0xd674  brfalse.s loc_D6E7
0xd676  ldarg.2
0xd677  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd67c  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticle::.ctor(valuetype [mscorlib]System.Guid)
0xd681  stloc.s  6
0xd683  ldloc.s  6
0xd685  ldstr    aIslatestversio// "islatestversion"
0xd68a  ldc.i4.1
0xd68b  box      [mscorlib]System.Boolean
0xd690  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0xd695  ldloc.s  6
0xd697  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xd69c  ldloc.s  5
0xd69e  callvirt instance var<u1> class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::get_Item1()
0xd6a3  box      [mscorlib]System.Guid
0xd6a8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0xd6ad  ldarg.2
0xd6ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd6b3  ldc.i4.s 0x1A
0xd6b5  ldstr    a0// "{0}"
0xd6ba  ldc.i4.1
0xd6bb  newarr   [mscorlib]System.Object
0xd6c0  dup
0xd6c1  ldc.i4.0
0xd6c2  ldstr    aMakingTheNextM// "Making the next max version ArticleId={"...
0xd6c7  ldloc.s  5
0xd6c9  callvirt instance var<u1> class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::get_Item1()
0xd6ce  box      [mscorlib]System.Guid
0xd6d3  call     string [mscorlib]System.String::Format(string, object)
0xd6d8  stelem.ref
0xd6d9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd6de  ldarg.0
0xd6df  ldloc.s  6
0xd6e1  ldarg.2
0xd6e2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd6e7  ret
```
