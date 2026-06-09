# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CreateKnowledgeArticleTranslation

- ea: `0xd960`
- end: `0xdc9e`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CreateKnowledgeArticleTranslation`
- size: `830`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0xd960`
- `0xe0f0`
- `0xf020`
- `0xf300`
- `0xf490`
- `0xfce0`
- `0x10130`
- `0x10190`

## pseudocode

```c

```

## disassembly

```asm
0xd960  ldarg.1
0xd961  ldstr    aEntityreferenc// "entityReference"
0xd966  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xd96b  ldarg.s  4
0xd96d  ldstr    aContext// "context"
0xd972  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xd977  ldarg.0
0xd978  ldarg.1
0xd979  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xd97e  ldstr    aKnowledgeartic// "KnowledgeArticle"
0xd983  ldarg.s  4
0xd985  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd98a  ldc.i4.1
0xd98b  ldarg.s  4
0xd98d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Clone(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CloneOptions, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xd992  stloc.0
0xd993  ldloc.0
0xd994  ldstr    aMajorversionnu// "majorversionnumber"
0xd999  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd99e  unbox.any [mscorlib]System.Int32
0xd9a3  stloc.1
0xd9a4  ldloc.0
0xd9a5  ldstr    aMinorversionnu// "minorversionnumber"
0xd9aa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd9af  unbox.any [mscorlib]System.Int32
0xd9b4  stloc.2
0xd9b5  ldloc.0
0xd9b6  ldstr    aIsprimary// "isprimary"
0xd9bb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd9c0  unbox.any [mscorlib]System.Boolean
0xd9c5  stloc.3
0xd9c6  ldloc.0
0xd9c7  ldstr    aLanguagelocale// "languagelocaleid"
0xd9cc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd9d1  unbox.any [mscorlib]System.Guid
0xd9d6  stloc.s  4
0xd9d8  ldloc.0
0xd9d9  ldstr    aContent// "content"
0xd9de  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd9e3  castclass [mscorlib]System.String
0xd9e8  brtrue.s loc_D9ED
0xd9ea  ldc.i4.0
0xd9eb  br.s     loc_DA02
0xd9ed  ldloc.0
0xd9ee  ldstr    aContent// "content"
0xd9f3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xd9f8  castclass [mscorlib]System.String
0xd9fd  callvirt instance int32 [mscorlib]System.String::get_Length()
0xda02  stloc.s  5
0xda04  ldarg.0
0xda05  ldarg.2
0xda06  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xda0b  ldarg.s  4
0xda0d  call     instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.LanguageLocale Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::GetLanguageLocaleEntity(valuetype [mscorlib]System.Guid languageLocaleID, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xda12  stloc.s  6
0xda14  ldloc.0
0xda15  ldstr    aIsprimary// "isprimary"
0xda1a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xda1f  unbox.any [mscorlib]System.Boolean
0xda24  brtrue.s loc_DA3B
0xda26  ldc.i4   0x80061402
0xda2b  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0xda30  ldc.i4   0x80061402
0xda35  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xda3a  throw
0xda3b  ldloc.s  6
0xda3d  brfalse.s loc_DA7C
0xda3f  ldloc.0
0xda40  ldstr    aLanguagelocale// "languagelocaleid"
0xda45  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xda4a  unbox.any [mscorlib]System.Guid
0xda4f  ldloc.s  6
0xda51  ldstr    aLanguagelocale// "languagelocaleid"
0xda56  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xda5b  unbox.any [mscorlib]System.Guid
0xda60  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xda65  brfalse.s loc_DA7C
0xda67  ldc.i4   0x80061403
0xda6c  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0xda71  ldc.i4   0x80061403
0xda76  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xda7b  throw
0xda7c  ldloc.0
0xda7d  ldstr    aIsprimary// "isprimary"
0xda82  ldc.i4.0
0xda83  box      [mscorlib]System.Boolean
0xda88  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xda8d  ldloc.0
0xda8e  ldstr    aParentarticlec// "parentarticlecontentid"
0xda93  ldarg.1
0xda94  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xda99  box      [mscorlib]System.Guid
0xda9e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdaa3  ldloc.0
0xdaa4  ldstr    aIslatestversio// "islatestversion"
0xdaa9  ldc.i4.1
0xdaaa  box      [mscorlib]System.Boolean
0xdaaf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdab4  ldarg.0
0xdab5  ldloc.0
0xdab6  ldstr    aArticlepublicn// "articlepublicnumber"
0xdabb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xdac0  castclass [mscorlib]System.String
0xdac5  ldarg.2
0xdac6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xdacb  ldarg.s  4
0xdacd  call     instance class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32> Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::FindMaxVersionOfKnowledgeArticle(string publicNumber, valuetype [mscorlib]System.Guid languageLocaleID, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xdad2  stloc.s  7
0xdad4  ldloc.s  7
0xdad6  brfalse.s loc_DB39
0xdad8  ldarg.3
0xdad9  brfalse.s loc_DB07
0xdadb  ldloc.0
0xdadc  ldstr    aMajorversionnu// "majorversionnumber"
0xdae1  ldloc.s  7
0xdae3  callvirt instance var<u1> class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::get_Item2()
0xdae8  ldc.i4.1
0xdae9  add
0xdaea  box      [mscorlib]System.Int32
0xdaef  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdaf4  ldloc.0
0xdaf5  ldstr    aMinorversionnu// "minorversionnumber"
0xdafa  ldc.i4.0
0xdafb  box      [mscorlib]System.Int32
0xdb00  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdb05  br.s     loc_DB5B
0xdb07  ldloc.0
0xdb08  ldstr    aMajorversionnu// "majorversionnumber"
0xdb0d  ldloc.s  7
0xdb0f  callvirt instance var<u1> class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::get_Item2()
0xdb14  box      [mscorlib]System.Int32
0xdb19  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdb1e  ldloc.0
0xdb1f  ldstr    aMinorversionnu// "minorversionnumber"
0xdb24  ldloc.s  7
0xdb26  callvirt instance var<u1> class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::get_Item3()
0xdb2b  ldc.i4.1
0xdb2c  add
0xdb2d  box      [mscorlib]System.Int32
0xdb32  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdb37  br.s     loc_DB5B
0xdb39  ldloc.0
0xdb3a  ldstr    aMajorversionnu// "majorversionnumber"
0xdb3f  ldc.i4.1
0xdb40  box      [mscorlib]System.Int32
0xdb45  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdb4a  ldloc.0
0xdb4b  ldstr    aMinorversionnu// "minorversionnumber"
0xdb50  ldc.i4.0
0xdb51  box      [mscorlib]System.Int32
0xdb56  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdb5b  ldloc.0
0xdb5c  ldstr    aStatecode// "statecode"
0xdb61  ldc.i4.0
0xdb62  box      [mscorlib]System.Int32
0xdb67  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdb6c  ldloc.s  6
0xdb6e  brfalse.s loc_DB89
0xdb70  ldloc.0
0xdb71  ldstr    aLanguagelocale// "languagelocaleid"
0xdb76  ldloc.s  6
0xdb78  ldstr    aLanguagelocale// "languagelocaleid"
0xdb7d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xdb82  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xdb87  br.s     loc_DB9F
0xdb89  ldstr    aLanguageLocale// "Language Locale entity with Locale Id "
0xdb8e  ldarg.2
0xdb8f  ldstr    aNotFound// " not found"
0xdb94  call     string [mscorlib]System.String::Concat(object, object, object)
0xdb99  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmObjectNotFoundException::.ctor(string)
0xdb9e  throw
0xdb9f  ldarg.s  4
0xdba1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0xdba6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0xdbab  ldarg.s  4
0xdbad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xdbb2  ldc.i4.s 0x1A
0xdbb4  ldstr    a0// "{0}"
0xdbb9  ldc.i4.1
0xdbba  newarr   [mscorlib]System.Object
0xdbbf  dup
0xdbc0  ldc.i4.0
0xdbc1  ldstr    aCreatingTransa// "Creating transaction for creation of kn"...
0xdbc6  ldarg.1
0xdbc7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xdbcc  box      [mscorlib]System.Guid
0xdbd1  call     string [mscorlib]System.String::Format(string, object)
0xdbd6  stelem.ref
0xdbd7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdbdc  ldarg.0
0xdbdd  ldloc.0
0xdbde  ldarg.s  4
0xdbe0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xdbe5  stloc.s  8
0xdbe7  ldarg.0
0xdbe8  ldloc.0
0xdbe9  ldloc.s  8
0xdbeb  ldarg.s  4
0xdbed  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CreateDocumentIndexRecord(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xdbf2  ldarg.0
0xdbf3  ldloc.s  8
0xdbf5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xdbfa  ldstr    aBd57803e040844// "BD57803E-0408-44D6-B21D-AE7158EC6555"
0xdbff  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xdc04  ldarg.s  4
0xdc06  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SwitchProcess(valuetype [mscorlib]System.Guid entityGuid, valuetype [mscorlib]System.Guid processGuid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xdc0b  ldarg.0
0xdc0c  ldloc.s  8
0xdc0e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xdc13  ldloc.0
0xdc14  ldstr    aArticlepublicn// "articlepublicnumber"
0xdc19  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xdc1e  castclass [mscorlib]System.String
0xdc23  ldarg.2
0xdc24  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xdc29  ldarg.s  4
0xdc2b  call     instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::UpdateKnowledgeArticleAsLatestVersion(valuetype [mscorlib]System.Guid knowledgeArticleID, string publicNumber, valuetype [mscorlib]System.Guid languageLocaleID, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xdc30  ldarg.s  4
0xdc32  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0xdc37  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0xdc3c  call     class Microsoft.Crm.Service.ObjectModel.KnowledgeArticleTelemetryEvents Microsoft.Crm.Service.ObjectModel.KnowledgeArticleTelemetryEvents::get_Instance()
0xdc41  ldloc.0
0xdc42  ldstr    aMajorversionnu// "majorversionnumber"
0xdc47  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xdc4c  unbox.any [mscorlib]System.Int32
0xdc51  ldloc.0
0xdc52  ldstr    aMinorversionnu// "minorversionnumber"
0xdc57  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xdc5c  unbox.any [mscorlib]System.Int32
0xdc61  ldloc.0
0xdc62  ldstr    aLanguagelocale// "languagelocaleid"
0xdc67  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xdc6c  unbox.any [mscorlib]System.Guid
0xdc71  ldc.i4.0
0xdc72  ldloc.1
0xdc73  ldloc.2
0xdc74  ldloc.s  4
0xdc76  ldloc.3
0xdc77  ldloc.s  5
0xdc79  ldarg.s  4
0xdc7b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xdc80  callvirt instance void Microsoft.Crm.Service.ObjectModel.KnowledgeArticleTelemetryEvents::LogKnowledgeArticleCreation(int32 major, int32 minor, valuetype [mscorlib]System.Guid languageLocaleId, bool isPrimary, int32 sourceMajor, int32 sourceMinor, valuetype [mscorlib]System.Guid sourceLanguageLocaleId, bool sourceIsPrimary, int32 sourceContentLength, valuetype [mscorlib]System.Guid orgId)
0xdc85  ldloc.s  8
0xdc87  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0xdc8c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xdc91  ldloc.s  8
0xdc93  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xdc98  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0xdc9d  ret
```
