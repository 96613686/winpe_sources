# <CommitUploadSession>d__5::MoveNext

- ea: `0x30050`
- end: `0x303b3`
- name: `<CommitUploadSession>d__5::MoveNext`
- size: `867`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0xd040`
- `0xd180`
- `0xd1a0`
- `0xd1c0`
- `0xd1e0`
- `0xd200`
- `0xd220`
- `0xd240`
- `0xd260`
- `0x24ed0`
- `0x30050`

## string_xrefs

- `0x300a3`: `prvCreateEntity`

## pseudocode

```c

```

## disassembly

```asm
0x30050  ldarg.0
0x30051  ldfld    int32 <CommitUploadSession>d__5::<>1__state
0x30056  stloc.0
0x30057  ldarg.0
0x30058  ldfld    class Microsoft.Crm.Extensibility.StorageService.StorageController <CommitUploadSession>d__5::<>4__this
0x3005d  stloc.1
0x3005e  ldloc.0
0x3005f  brfalse.s loc_30077
0x30061  ldloc.1
0x30062  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x30067  ldc.i4   0x1F5
0x3006c  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Net.Http.Formatting]System.Net.Http.HttpRequestMessageExtensions::CreateResponse(class [System.Net.Http]System.Net.Http.HttpRequestMessage, valuetype [System]System.Net.HttpStatusCode)
0x30071  stloc.2
0x30072  leave    loc_3039E
0x30077  nop
0x30078  ldloc.0
0x30079  pop
0x3007a  nop
0x3007b  ldloc.0
0x3007c  brfalse  loc_3010D
0x30081  ldarg.0
0x30082  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CommitUploadSession>d__5::<eContext>5__2
0x30087  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0x3008c  ldc.i4.0
0x3008d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x30092  ldarg.0
0x30093  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CommitUploadSession>d__5::<eContext>5__2
0x30098  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x3009d  ldloc.3
0x3009e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x300a3  ldstr    aPrvcreateentit// "prvCreateEntity"
0x300a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x300ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x300b2  ldarg.0
0x300b3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CommitUploadSession>d__5::<eContext>5__2
0x300b8  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x300bd  ldarg.0
0x300be  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x300c3  callvirt instance string Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_SasURI()
0x300c8  ldarg.0
0x300c9  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x300ce  callvirt instance string Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_FileName()
0x300d3  ldloc.3
0x300d4  call     class [mscorlib]System.Threading.Tasks.Task [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalStorage.UploadService::CommitFileUpload(string, string, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext)
0x300d9  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x300de  stloc.s  5
0x300e0  ldloca.s 5
0x300e2  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x300e7  brtrue.s loc_3012A
0x300e9  ldarg.0
0x300ea  ldc.i4.0
0x300eb  dup
0x300ec  stloc.0
0x300ed  stfld    int32 <CommitUploadSession>d__5::<>1__state
0x300f2  ldarg.0
0x300f3  ldloc.s  5
0x300f5  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CommitUploadSession>d__5::<>u__1
0x300fa  ldarg.0
0x300fb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <CommitUploadSession>d__5::<>t__builder
0x30100  ldloca.s 5
0x30102  ldarg.0
0x30103  call     T0x2B000116
0x30108  leave    loc_303B2
0x3010d  ldarg.0
0x3010e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CommitUploadSession>d__5::<>u__1
0x30113  stloc.s  5
0x30115  ldarg.0
0x30116  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CommitUploadSession>d__5::<>u__1
0x3011b  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x30121  ldarg.0
0x30122  ldc.i4.m1
0x30123  dup
0x30124  stloc.0
0x30125  stfld    int32 <CommitUploadSession>d__5::<>1__state
0x3012a  ldloca.s 5
0x3012c  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x30131  ldloca.s 4
0x30133  initobj  [mscorlib]System.Guid
0x30139  ldloc.3
0x3013a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3013f  ldc.i4.0
0x30140  ldc.i4.0
0x30141  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x30146  stloc.s  6
0x30148  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0x3014d  stloc.s  7
0x3014f  ldloc.s  6
0x30151  ldloc.s  7
0x30153  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_UserId()
0x30158  ldc.i4.1
0x30159  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x3015e  ldloca.s 8
0x30160  ldarg.0
0x30161  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x30166  callvirt instance string Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_SasURI()
0x3016b  newobj   instance void [System]System.Uri::.ctor(string)
0x30170  call     instance string[] [System]System.Uri::get_Segments()
0x30175  ldc.i4.2
0x30176  ldelem.ref
0x30177  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3017c  ldarg.0
0x3017d  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x30182  callvirt instance int32 Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_AttachmentType()
0x30187  ldc.i4.5
0x30188  bne.un   loc_30269
0x3018d  ldloc.3
0x3018e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x30193  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Annotation::.ctor(valuetype [mscorlib]System.Guid)
0x30198  stloc.s  9
0x3019a  ldloc.s  9
0x3019c  ldstr    aMimetype// "mimetype"
0x301a1  ldstr    aApplicationOct// "application/octet-stream"
0x301a6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x301ab  ldloc.s  9
0x301ad  ldstr    aFilename// "filename"
0x301b2  ldarg.0
0x301b3  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x301b8  callvirt instance string Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_FileName()
0x301bd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x301c2  ldloc.s  9
0x301c4  ldstr    aFilesize// "filesize"
0x301c9  ldarg.0
0x301ca  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x301cf  callvirt instance int32 Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_FileSize()
0x301d4  box      [mscorlib]System.Int32
0x301d9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x301de  ldloc.s  9
0x301e0  ldstr    aDocumentbody// "documentbody"
0x301e5  ldarg.0
0x301e6  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x301eb  callvirt instance int32 Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_AttachmentType()
0x301f0  ldloc.s  8
0x301f2  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalStorage.ExternalStorageUtilities::CreateStorageFileName(int32, valuetype [mscorlib]System.Guid)
0x301f7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x301fc  ldarg.0
0x301fd  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x30202  callvirt instance string Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_Title()
0x30207  brfalse.s loc_30220
0x30209  ldloc.s  9
0x3020b  ldstr    aSubject// "subject"
0x30210  ldarg.0
0x30211  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x30216  callvirt instance string Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_Title()
0x3021b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x30220  ldarg.0
0x30221  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x30226  callvirt instance string Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_Description()
0x3022b  brfalse.s loc_30244
0x3022d  ldloc.s  9
0x3022f  ldstr    aNotetext// "notetext"
0x30234  ldarg.0
0x30235  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x3023a  callvirt instance string Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_Description()
0x3023f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x30244  ldloc.s  9
0x30246  stloc.s  0xA
0x30248  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AnnotationService::.ctor()
0x3024d  ldloc.s  0xA
0x3024f  ldloc.s  6
0x30251  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AnnotationServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UpgradingOff>::CreateEntryForEFS(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x30256  ldloc.s  6
0x30258  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x3025d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x30262  stloc.s  4
0x30264  br       loc_30326
0x30269  ldloc.3
0x3026a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3026f  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ActivityMimeAttachment::.ctor(valuetype [mscorlib]System.Guid)
0x30274  dup
0x30275  ldstr    aMimetype// "mimetype"
0x3027a  ldstr    aApplicationOct// "application/octet-stream"
0x3027f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x30284  dup
0x30285  ldstr    aFilename// "filename"
0x3028a  ldarg.0
0x3028b  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x30290  callvirt instance string Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_FileName()
0x30295  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3029a  dup
0x3029b  ldstr    aFilesize// "filesize"
0x302a0  ldarg.0
0x302a1  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x302a6  callvirt instance int32 Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_FileSize()
0x302ab  box      [mscorlib]System.Int32
0x302b0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x302b5  dup
0x302b6  ldstr    aObjectid// "objectid"
0x302bb  ldarg.0
0x302bc  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x302c1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_ParentObjectId()
0x302c6  box      [mscorlib]System.Guid
0x302cb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x302d0  dup
0x302d1  ldstr    aObjecttypecode// "objecttypecode"
0x302d6  ldarg.0
0x302d7  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x302dc  callvirt instance int32 Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_ParentObjectType()
0x302e1  box      [mscorlib]System.Int32
0x302e6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x302eb  dup
0x302ec  ldstr    aBody// "body"
0x302f1  ldarg.0
0x302f2  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CommitUploadSession>d__5::metadata
0x302f7  callvirt instance int32 Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_AttachmentType()
0x302fc  ldloc.s  8
0x302fe  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalStorage.ExternalStorageUtilities::CreateStorageFileName(int32, valuetype [mscorlib]System.Guid)
0x30303  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x30308  stloc.s  0xB
0x3030a  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityMimeAttachmentService::.ctor()
0x3030f  ldloc.s  0xB
0x30311  ldloc.s  6
0x30313  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ActivityMimeAttachmentService::CreateEntryForEFS(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x30318  ldloc.s  6
0x3031a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x3031f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x30324  stloc.s  4
0x30326  ldloc.1
0x30327  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x3032c  ldc.i4   0xC9
0x30331  ldloca.s 4
0x30333  ldstr    aD_0// "D"
0x30338  call     instance string [mscorlib]System.Guid::ToString(string)
0x3033d  call     T0x2B000115
0x30342  stloc.2
0x30343  leave.s  loc_3039E
0x30345  ldloc.0
0x30346  ldc.i4.0
0x30347  bge.s    loc_30354
0x30349  ldloc.s  6
0x3034b  brfalse.s loc_30354
0x3034d  ldloc.s  6
0x3034f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x30354  endfinally
0x30355  stloc.s  0xC
0x30357  ldarg.0
0x30358  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CommitUploadSession>d__5::<eContext>5__2
0x3035d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x30362  ldloc.1
0x30363  ldloc.s  0xC
0x30365  call     instance class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.Crm.Extensibility.StorageService.StorageController::HandleException(class [mscorlib]System.Exception e)
0x3036a  stloc.2
0x3036b  leave.s  loc_3039E
0x3036d  ldloc.0
0x3036e  ldc.i4.0
0x3036f  bge.s    loc_30384
0x30371  ldarg.0
0x30372  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CommitUploadSession>d__5::<eContext>5__2
0x30377  brfalse.s loc_30384
0x30379  ldarg.0
0x3037a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CommitUploadSession>d__5::<eContext>5__2
0x3037f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x30384  endfinally
0x30385  stloc.s  0xD
0x30387  ldarg.0
0x30388  ldc.i4.s 0xFE
0x3038a  stfld    int32 <CommitUploadSession>d__5::<>1__state
0x3038f  ldarg.0
0x30390  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <CommitUploadSession>d__5::<>t__builder
0x30395  ldloc.s  0xD
0x30397  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0x3039c  leave.s  loc_303B2
0x3039e  ldarg.0
0x3039f  ldc.i4.s 0xFE
0x303a1  stfld    int32 <CommitUploadSession>d__5::<>1__state
0x303a6  ldarg.0
0x303a7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <CommitUploadSession>d__5::<>t__builder
0x303ac  ldloc.2
0x303ad  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0x303b2  ret
```
