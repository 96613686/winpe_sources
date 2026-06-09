# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::Create

- ea: `0xcf30`
- end: `0xd1b1`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::Create`
- size: `641`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0xcf30`
- `0xe0f0`
- `0xf800`
- `0xfa80`
- `0xfc40`
- `0xfc90`
- `0x10130`
- `0x10190`

## pseudocode

```c

```

## disassembly

```asm
0xcf30  ldarg.1
0xcf31  ldstr    aEntity// "entity"
0xcf36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xcf3b  ldarg.2
0xcf3c  ldstr    aContext// "context"
0xcf41  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xcf46  ldnull
0xcf47  stloc.0
0xcf48  ldarg.2
0xcf49  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xcf4e  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticle::.ctor(valuetype [mscorlib]System.Guid)
0xcf53  stloc.1
0xcf54  ldarg.1
0xcf55  ldstr    aLanguagelocale// "languagelocaleid"
0xcf5a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcf5f  brtrue.s loc_CFB4
0xcf61  ldarg.2
0xcf62  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcf67  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationSettings()
0xcf6c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization::get_LanguageCode()
0xcf71  stloc.3
0xcf72  ldarg.0
0xcf73  ldloc.3
0xcf74  ldarg.2
0xcf75  call     instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.LanguageLocale Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::GetLanguageLocaleEntity(int32 lcid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xcf7a  stloc.s  4
0xcf7c  ldloc.s  4
0xcf7e  brfalse.s loc_CF99
0xcf80  ldarg.1
0xcf81  ldstr    aLanguagelocale// "languagelocaleid"
0xcf86  ldloc.s  4
0xcf88  ldstr    aLanguagelocale// "languagelocaleid"
0xcf8d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xcf92  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcf97  br.s     loc_CFB4
0xcf99  ldstr    aLanguageLocale// "Language Locale entity with Locale Id "
0xcf9e  ldloc.3
0xcf9f  box      [mscorlib]System.Int32
0xcfa4  ldstr    aNotFound// " not found"
0xcfa9  call     string [mscorlib]System.String::Concat(object, object, object)
0xcfae  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmObjectNotFoundException::.ctor(string)
0xcfb3  throw
0xcfb4  ldarg.1
0xcfb5  ldstr    aParentarticlec// "parentarticlecontentid"
0xcfba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcfbf  brtrue   loc_D12C
0xcfc4  ldarg.1
0xcfc5  ldstr    aArticlepublicn// "articlepublicnumber"
0xcfca  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcfcf  brtrue.s loc_CFFC
0xcfd1  ldarg.2
0xcfd2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xcfd7  ldc.i4.s 0x1A
0xcfd9  ldstr    a0// "{0}"
0xcfde  ldc.i4.1
0xcfdf  newarr   [mscorlib]System.Object
0xcfe4  dup
0xcfe5  ldc.i4.0
0xcfe6  ldstr    aArticlePublicN// "Article Public Number can not be null"
0xcfeb  ldc.i4.0
0xcfec  newarr   [mscorlib]System.Object
0xcff1  call     string [mscorlib]System.String::Format(string, object[])
0xcff6  stelem.ref
0xcff7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcffc  ldarg.0
0xcffd  ldarg.1
0xcffe  ldstr    aArticlepublicn// "articlepublicnumber"
0xd003  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd008  callvirt instance string [mscorlib]System.Object::ToString()
0xd00d  ldarg.2
0xd00e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetrieveRootKnowledgeArticlesByPublicNumber(string publicArticleNumber, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd013  stloc.s  5
0xd015  ldloc.s  5
0xd017  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xd01c  brtrue.s loc_D06D
0xd01e  ldarg.0
0xd01f  ldloc.1
0xd020  ldarg.2
0xd021  ldarg.1
0xd022  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CreateRootKnowledgeArticle(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity rootEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity actualEntity)
0xd027  stloc.s  6
0xd029  ldarg.1
0xd02a  ldstr    aParentarticlec// "parentarticlecontentid"
0xd02f  ldloc.s  6
0xd031  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd036  box      [mscorlib]System.Guid
0xd03b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xd040  ldarg.1
0xd041  ldstr    aRootarticleid// "rootarticleid"
0xd046  ldloc.s  6
0xd048  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xd04d  box      [mscorlib]System.Guid
0xd052  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xd057  ldarg.1
0xd058  ldstr    aIsprimary// "isprimary"
0xd05d  ldc.i4.1
0xd05e  box      [mscorlib]System.Boolean
0xd063  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xd068  br       loc_D11B
0xd06d  ldloc.s  5
0xd06f  ldc.i4.0
0xd070  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xd075  brfalse  loc_D11B
0xd07a  ldarg.1
0xd07b  ldstr    aParentarticlec// "parentarticlecontentid"
0xd080  ldloc.s  5
0xd082  ldc.i4.0
0xd083  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xd088  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xd08d  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xd092  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xd097  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0xd09c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xd0a1  ldarg.1
0xd0a2  ldstr    aRootarticleid// "rootarticleid"
0xd0a7  ldloc.s  5
0xd0a9  ldc.i4.0
0xd0aa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xd0af  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0xd0b4  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xd0b9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0xd0be  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0xd0c3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xd0c8  ldloc.s  5
0xd0ca  ldc.i4.0
0xd0cb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xd0d0  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticle
0xd0d5  stloc.1
0xd0d6  ldloc.1
0xd0d7  ldstr    aLanguagelocale// "languagelocaleid"
0xd0dc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd0e1  brfalse.s loc_D11B
0xd0e3  ldarg.1
0xd0e4  ldstr    aLanguagelocale// "languagelocaleid"
0xd0e9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd0ee  callvirt instance string [mscorlib]System.Object::ToString()
0xd0f3  ldloc.1
0xd0f4  ldstr    aLanguagelocale// "languagelocaleid"
0xd0f9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd0fe  callvirt instance string [mscorlib]System.Object::ToString()
0xd103  callvirt instance bool [mscorlib]System.String::Equals(string)
0xd108  brfalse.s loc_D11B
0xd10a  ldarg.1
0xd10b  ldstr    aIsprimary// "isprimary"
0xd110  ldc.i4.1
0xd111  box      [mscorlib]System.Boolean
0xd116  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xd11b  ldarg.1
0xd11c  ldstr    aIslatestversio// "islatestversion"
0xd121  ldc.i4.1
0xd122  box      [mscorlib]System.Boolean
0xd127  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xd12c  ldarg.0
0xd12d  ldarg.1
0xd12e  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::ParseUnsafeContent(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity)
0xd133  ldarg.0
0xd134  ldarg.1
0xd135  ldarg.2
0xd136  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd13b  stloc.0
0xd13c  ldarg.0
0xd13d  ldarg.1
0xd13e  ldloc.0
0xd13f  ldarg.2
0xd140  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CreateDocumentIndexRecord(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xd145  ldarg.1
0xd146  ldstr    aContent// "content"
0xd14b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd150  brfalse.s loc_D169
0xd152  ldarg.1
0xd153  ldstr    aContent// "content"
0xd158  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd15d  castclass [mscorlib]System.String
0xd162  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd167  br.s     loc_D16A
0xd169  ldc.i4.0
0xd16a  stloc.2
0xd16b  ldloc.1
0xd16c  ldstr    aLanguagelocale// "languagelocaleid"
0xd171  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd176  brfalse.s loc_D1AF
0xd178  call     class Microsoft.Crm.Service.ObjectModel.KnowledgeArticleTelemetryEvents Microsoft.Crm.Service.ObjectModel.KnowledgeArticleTelemetryEvents::get_Instance()
0xd17d  ldc.i4.1
0xd17e  ldc.i4.0
0xd17f  ldarg.1
0xd180  ldstr    aLanguagelocale// "languagelocaleid"
0xd185  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xd18a  unbox.any [mscorlib]System.Guid
0xd18f  ldc.i4.1
0xd190  ldc.i4.0
0xd191  ldc.i4.0
0xd192  ldloc.1
0xd193  ldstr    aLanguagelocale// "languagelocaleid"
0xd198  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd19d  unbox.any [mscorlib]System.Guid
0xd1a2  ldc.i4.0
0xd1a3  ldloc.2
0xd1a4  ldarg.2
0xd1a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd1aa  callvirt instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleTelemetryEvents::LogKnowledgeArticleCreation(int32 major, int32 minor, valuetype [mscorlib]System.Guid languageLocaleId, bool isPrimary, int32 sourceMajor, int32 sourceMinor, valuetype [mscorlib]System.Guid sourceLanguageLocaleId, bool sourceIsPrimary, int32 sourceContentLength, valuetype [mscorlib]System.Guid orgId)
0xd1af  ldloc.0
0xd1b0  ret
```
