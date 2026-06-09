# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CreateDocumentIndexRecord

- ea: `0xe0f0`
- end: `0xe2d7`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::CreateDocumentIndexRecord`
- size: `487`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xcf30`
- `0xd6f0`
- `0xd960`

## callees

- `0x61a0`
- `0xafd0`
- `0xe0f0`
- `0xe460`

## pseudocode

```c

```

## disassembly

```asm
0xe0f0  ldarg.3
0xe0f1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xe0f6  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.DocumentIndex::.ctor(valuetype [mscorlib]System.Guid)
0xe0fb  stloc.0
0xe0fc  newobj   instance void Microsoft.Crm.Service.ObjectModel.DocumentIndexService::.ctor()
0xe101  stloc.1
0xe102  ldarg.1
0xe103  ldstr    aSubjectid// "subjectid"
0xe108  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe10d  brfalse.s loc_E12A
0xe10f  ldloc.0
0xe110  ldstr    aSubjectid// "subjectid"
0xe115  ldarg.1
0xe116  ldstr    aSubjectid// "subjectid"
0xe11b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe120  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe125  br       loc_E1B1
0xe12a  ldstr    aSubject_0// "Subject"
0xe12f  ldarg.3
0xe130  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xe135  stloc.2
0xe136  ldloc.2
0xe137  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0xe13c  ldc.i4.1
0xe13d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_Count(int32)
0xe142  ldloc.2
0xe143  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0xe148  ldc.i4.1
0xe149  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_PageNumber(int32)
0xe14e  ldarg.0
0xe14f  ldloc.2
0xe150  ldarg.3
0xe151  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe156  stloc.3
0xe157  ldloc.3
0xe158  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xe15d  ldc.i4.0
0xe15e  ble.s    loc_E17E
0xe160  ldloc.0
0xe161  ldstr    aSubjectid// "subjectid"
0xe166  ldloc.3
0xe167  ldc.i4.0
0xe168  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xe16d  ldstr    aSubjectid// "subjectid"
0xe172  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xe177  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe17c  br.s     loc_E1B1
0xe17e  ldarg.3
0xe17f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xe184  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Subject::.ctor(valuetype [mscorlib]System.Guid)
0xe189  stloc.s  4
0xe18b  newobj   instance void Microsoft.Crm.Service.ObjectModel.SubjectService::.ctor()
0xe190  ldloc.s  4
0xe192  ldarg.3
0xe193  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe198  stloc.s  5
0xe19a  ldloc.0
0xe19b  ldstr    aSubjectid// "subjectid"
0xe1a0  ldloc.s  5
0xe1a2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xe1a7  box      [mscorlib]System.Guid
0xe1ac  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe1b1  ldloc.0
0xe1b2  ldstr    aDocumenttypeco// "documenttypecode"
0xe1b7  ldc.i4.1
0xe1b8  box      [mscorlib]System.Int32
0xe1bd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe1c2  ldloc.0
0xe1c3  ldstr    aDocumentid// "documentid"
0xe1c8  ldarg.2
0xe1c9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xe1ce  box      [mscorlib]System.Guid
0xe1d3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe1d8  ldloc.0
0xe1d9  ldstr    aIslatestversio// "islatestversion"
0xe1de  ldarg.1
0xe1df  ldstr    aIslatestversio// "islatestversion"
0xe1e4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe1e9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe1ee  ldloc.0
0xe1ef  ldstr    aIspublished// "ispublished"
0xe1f4  ldc.i4.1
0xe1f5  box      [mscorlib]System.Boolean
0xe1fa  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe1ff  ldloc.0
0xe200  ldstr    aSearchtext// "searchtext"
0xe205  ldstr    a01234// "{0} {1} {2} {3} {4}"
0xe20a  ldc.i4.5
0xe20b  newarr   [mscorlib]System.Object
0xe210  dup
0xe211  ldc.i4.0
0xe212  ldarg.0
0xe213  ldarg.1
0xe214  ldstr    aContent// "content"
0xe219  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe21e  castclass [mscorlib]System.String
0xe223  call     instance string Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::SanitizeExtractedSearchTextFromHtml(string html)
0xe228  stelem.ref
0xe229  dup
0xe22a  ldc.i4.1
0xe22b  ldarg.1
0xe22c  ldstr    aTitle// "title"
0xe231  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe236  castclass [mscorlib]System.String
0xe23b  stelem.ref
0xe23c  dup
0xe23d  ldc.i4.2
0xe23e  ldarg.1
0xe23f  ldstr    aKeywords// "keywords"
0xe244  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe249  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xe24e  beq.s    loc_E262
0xe250  ldarg.1
0xe251  ldstr    aKeywords// "keywords"
0xe256  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe25b  castclass [mscorlib]System.String
0xe260  br.s     loc_E267
0xe262  ldstr    asc_1EEAE// ""
0xe267  stelem.ref
0xe268  dup
0xe269  ldc.i4.3
0xe26a  ldarg.1
0xe26b  ldstr    aArticlepublicn// "articlepublicnumber"
0xe270  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe275  castclass [mscorlib]System.String
0xe27a  stelem.ref
0xe27b  dup
0xe27c  ldc.i4.4
0xe27d  ldarg.1
0xe27e  ldstr    aDescription// "description"
0xe283  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe288  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xe28d  beq.s    loc_E2A1
0xe28f  ldarg.1
0xe290  ldstr    aDescription// "description"
0xe295  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xe29a  castclass [mscorlib]System.String
0xe29f  br.s     loc_E2A6
0xe2a1  ldstr    asc_1EEAE// ""
0xe2a6  stelem.ref
0xe2a7  call     string [mscorlib]System.String::Format(string, object[])
0xe2ac  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe2b1  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0xe2b6  brfalse.s loc_E2CD
0xe2b8  ldloc.0
0xe2b9  ldstr    aDocumentindexi// "documentindexid"
0xe2be  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0xe2c3  box      [mscorlib]System.Guid
0xe2c8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe2cd  ldloc.1
0xe2ce  ldloc.0
0xe2cf  ldarg.3
0xe2d0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe2d5  pop
0xe2d6  ret
```
