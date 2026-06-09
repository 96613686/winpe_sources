# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CreateKnowledgeArticleVersion

- ea: `0xd6f0`
- end: `0xd951`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CreateKnowledgeArticleVersion`
- size: `609`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0xd6f0`
- `0xe0f0`
- `0xedc0`
- `0xef10`
- `0xf020`
- `0xf300`
- `0xf490`
- `0x10130`
- `0x10190`

## pseudocode

```c

```

## disassembly

```asm
0xd6f0  ldarg.1
0xd6f1  ldstr    aEntity// "entity"
0xd6f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xd6fb  ldarg.3
0xd6fc  ldstr    aContext// "context"
0xd701  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xd706  ldarg.0
0xd707  ldarg.1
0xd708  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xd70d  ldstr    aKnowledgeartic// "KnowledgeArticle"
0xd712  ldarg.3
0xd713  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd718  ldc.i4.1
0xd719  ldarg.3
0xd71a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Clone(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CloneOptions, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd71f  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticle
0xd724  stloc.0
0xd725  ldloc.0
0xd726  ldstr    aLanguagelocale// "languagelocaleid"
0xd72b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd730  unbox.any [mscorlib]System.Guid
0xd735  stloc.1
0xd736  ldloc.0
0xd737  ldstr    aContent// "content"
0xd73c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd741  brtrue.s loc_D746
0xd743  ldc.i4.0
0xd744  br.s     loc_D75B
0xd746  ldloc.0
0xd747  ldstr    aContent// "content"
0xd74c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd751  castclass [mscorlib]System.String
0xd756  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd75b  stloc.2
0xd75c  ldloc.0
0xd75d  ldstr    aPreviousarticl// "previousarticlecontentid"
0xd762  ldarg.1
0xd763  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xd768  box      [mscorlib]System.Guid
0xd76d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xd772  ldloc.0
0xd773  ldstr    aIsrootarticle// "isrootarticle"
0xd778  ldc.i4.0
0xd779  box      [mscorlib]System.Boolean
0xd77e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xd783  ldloc.0
0xd784  ldstr    aIslatestversio// "islatestversion"
0xd789  ldc.i4.1
0xd78a  box      [mscorlib]System.Boolean
0xd78f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xd794  ldarg.0
0xd795  ldloc.0
0xd796  ldstr    aArticlepublicn// "articlepublicnumber"
0xd79b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd7a0  castclass [mscorlib]System.String
0xd7a5  ldloc.0
0xd7a6  ldstr    aLanguagelocale// "languagelocaleid"
0xd7ab  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd7b0  unbox.any [mscorlib]System.Guid
0xd7b5  ldarg.3
0xd7b6  call     instance class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32> Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::FindMaxVersionOfKnowledgeArticle(string publicNumber, valuetype [mscorlib]System.Guid languageLocaleID, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd7bb  stloc.3
0xd7bc  ldarg.2
0xd7bd  brfalse.s loc_D7EA
0xd7bf  ldloc.0
0xd7c0  ldstr    aMajorversionnu// "majorversionnumber"
0xd7c5  ldloc.3
0xd7c6  callvirt instance var<u1> class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::get_Item2()
0xd7cb  ldc.i4.1
0xd7cc  add
0xd7cd  box      [mscorlib]System.Int32
0xd7d2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xd7d7  ldloc.0
0xd7d8  ldstr    aMinorversionnu// "minorversionnumber"
0xd7dd  ldc.i4.0
0xd7de  box      [mscorlib]System.Int32
0xd7e3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xd7e8  br.s     loc_D818
0xd7ea  ldloc.0
0xd7eb  ldstr    aMajorversionnu// "majorversionnumber"
0xd7f0  ldloc.3
0xd7f1  callvirt instance var<u1> class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::get_Item2()
0xd7f6  box      [mscorlib]System.Int32
0xd7fb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xd800  ldloc.0
0xd801  ldstr    aMinorversionnu// "minorversionnumber"
0xd806  ldloc.3
0xd807  callvirt instance var<u1> class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::get_Item3()
0xd80c  ldc.i4.1
0xd80d  add
0xd80e  box      [mscorlib]System.Int32
0xd813  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xd818  ldloc.0
0xd819  ldstr    aStatecode// "statecode"
0xd81e  ldc.i4.0
0xd81f  box      [mscorlib]System.Int32
0xd824  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xd829  ldarg.0
0xd82a  ldloc.0
0xd82b  ldarg.3
0xd82c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd831  stloc.s  4
0xd833  ldarg.0
0xd834  ldloc.0
0xd835  ldloc.s  4
0xd837  ldarg.3
0xd838  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CreateDocumentIndexRecord(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd83d  ldloc.0
0xd83e  ldstr    aIsprimary// "isprimary"
0xd843  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd848  unbox.any [mscorlib]System.Boolean
0xd84d  brfalse.s loc_D869
0xd84f  ldarg.0
0xd850  ldloc.s  4
0xd852  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd857  ldstr    aAb81c1af1a4548// "AB81C1AF-1A45-48D9-8133-3EDC033DBEEF"
0xd85c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd861  ldarg.3
0xd862  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SwitchProcess(valuetype [mscorlib]System.Guid entityGuid, valuetype [mscorlib]System.Guid processGuid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd867  br.s     loc_D881
0xd869  ldarg.0
0xd86a  ldloc.s  4
0xd86c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd871  ldstr    aBd57803e040844// "BD57803E-0408-44D6-B21D-AE7158EC6555"
0xd876  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd87b  ldarg.3
0xd87c  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SwitchProcess(valuetype [mscorlib]System.Guid entityGuid, valuetype [mscorlib]System.Guid processGuid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd881  ldarg.0
0xd882  ldloc.s  4
0xd884  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd889  ldloc.0
0xd88a  ldstr    aArticlepublicn// "articlepublicnumber"
0xd88f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd894  castclass [mscorlib]System.String
0xd899  ldloc.0
0xd89a  ldstr    aLanguagelocale// "languagelocaleid"
0xd89f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd8a4  unbox.any [mscorlib]System.Guid
0xd8a9  ldarg.3
0xd8aa  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::UpdateKnowledgeArticleAsLatestVersion(valuetype [mscorlib]System.Guid knowledgeArticleID, string publicNumber, valuetype [mscorlib]System.Guid languageLocaleID, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd8af  ldarg.0
0xd8b0  ldarg.1
0xd8b1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xd8b6  ldloc.s  4
0xd8b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd8bd  ldc.i4.0
0xd8be  ldarg.3
0xd8bf  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CopyRelatedCategoriesFromSourceToTargetKnowledgeArticle(valuetype [mscorlib]System.Guid sourceKnowledgeArticleId, valuetype [mscorlib]System.Guid targetKnowledgeArticleId, bool clearExistingCategoriesBeforeCopy, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd8c4  ldarg.0
0xd8c5  ldarg.1
0xd8c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xd8cb  ldloc.s  4
0xd8cd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd8d2  ldc.i4.0
0xd8d3  ldarg.3
0xd8d4  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CopyRelatedProductsFromSourceToTargetKnowledgeArticle(valuetype [mscorlib]System.Guid sourceKnowledgeArticleId, valuetype [mscorlib]System.Guid targetKnowledgeArticleId, bool clearExistingProductsBeforeCopy, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd8d9  call     class Microsoft.Crm.Service.ObjectModel.KnowledgeArticleTelemetryEvents Microsoft.Crm.Service.ObjectModel.KnowledgeArticleTelemetryEvents::get_Instance()
0xd8de  ldloc.0
0xd8df  ldstr    aMajorversionnu// "majorversionnumber"
0xd8e4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd8e9  unbox.any [mscorlib]System.Int32
0xd8ee  ldloc.0
0xd8ef  ldstr    aMinorversionnu// "minorversionnumber"
0xd8f4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd8f9  unbox.any [mscorlib]System.Int32
0xd8fe  ldloc.1
0xd8ff  ldloc.0
0xd900  ldstr    aIsprimary// "isprimary"
0xd905  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd90a  unbox.any [mscorlib]System.Boolean
0xd90f  ldloc.3
0xd910  callvirt instance var<u1> class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::get_Item2()
0xd915  ldloc.3
0xd916  callvirt instance var<u1> class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::get_Item3()
0xd91b  ldloc.1
0xd91c  ldloc.0
0xd91d  ldstr    aIsprimary// "isprimary"
0xd922  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd927  unbox.any [mscorlib]System.Boolean
0xd92c  ldloc.2
0xd92d  ldarg.3
0xd92e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd933  callvirt instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleTelemetryEvents::LogKnowledgeArticleCreation(int32 major, int32 minor, valuetype [mscorlib]System.Guid languageLocaleId, bool isPrimary, int32 sourceMajor, int32 sourceMinor, valuetype [mscorlib]System.Guid sourceLanguageLocaleId, bool sourceIsPrimary, int32 sourceContentLength, valuetype [mscorlib]System.Guid orgId)
0xd938  ldloc.s  4
0xd93a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0xd93f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xd944  ldloc.s  4
0xd946  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd94b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0xd950  ret
```
