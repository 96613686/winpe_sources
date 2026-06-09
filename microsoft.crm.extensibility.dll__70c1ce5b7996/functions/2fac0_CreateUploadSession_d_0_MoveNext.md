# <CreateUploadSession>d__0::MoveNext

- ea: `0x2fac0`
- end: `0x2fc1c`
- name: `<CreateUploadSession>d__0::MoveNext`
- size: `348`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xd040`
- `0xd090`
- `0x24ed0`
- `0x2fac0`

## string_xrefs

- `0x2fb13`: `prvCreateEntity`

## pseudocode

```c

```

## disassembly

```asm
0x2fac0  ldarg.0
0x2fac1  ldfld    int32 <CreateUploadSession>d__0::<>1__state
0x2fac6  stloc.0
0x2fac7  ldarg.0
0x2fac8  ldfld    class Microsoft.Crm.Extensibility.StorageService.StorageController <CreateUploadSession>d__0::<>4__this
0x2facd  stloc.1
0x2face  ldloc.0
0x2facf  brfalse.s loc_2FAE7
0x2fad1  ldloc.1
0x2fad2  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x2fad7  ldc.i4   0x1F5
0x2fadc  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Net.Http.Formatting]System.Net.Http.HttpRequestMessageExtensions::CreateResponse(class [System.Net.Http]System.Net.Http.HttpRequestMessage, valuetype [System]System.Net.HttpStatusCode)
0x2fae1  stloc.2
0x2fae2  leave    loc_2FC07
0x2fae7  nop
0x2fae8  ldloc.0
0x2fae9  pop
0x2faea  nop
0x2faeb  ldloc.0
0x2faec  brfalse  loc_2FB72
0x2faf1  ldarg.0
0x2faf2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CreateUploadSession>d__0::<eContext>5__2
0x2faf7  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0x2fafc  ldc.i4.0
0x2fafd  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x2fb02  ldarg.0
0x2fb03  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CreateUploadSession>d__0::<eContext>5__2
0x2fb08  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x2fb0d  ldloc.3
0x2fb0e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2fb13  ldstr    aPrvcreateentit// "prvCreateEntity"
0x2fb18  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x2fb1d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x2fb22  ldarg.0
0x2fb23  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CreateUploadSession>d__0::<eContext>5__2
0x2fb28  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2fb2d  ldarg.0
0x2fb2e  ldfld    class Microsoft.Crm.Extensibility.StorageService.CreateUploadSessionRequestMetadata <CreateUploadSession>d__0::metadata
0x2fb33  callvirt instance int64 Microsoft.Crm.Extensibility.StorageService.CreateUploadSessionRequestMetadata::get_FileSize()
0x2fb38  ldloc.3
0x2fb39  call     class [mscorlib]System.Threading.Tasks.Task`1<string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalStorage.UploadService::CreateUploadSession(int64, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext)
0x2fb3e  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x2fb43  stloc.s  5
0x2fb45  ldloca.s 5
0x2fb47  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x2fb4c  brtrue.s loc_2FB8F
0x2fb4e  ldarg.0
0x2fb4f  ldc.i4.0
0x2fb50  dup
0x2fb51  stloc.0
0x2fb52  stfld    int32 <CreateUploadSession>d__0::<>1__state
0x2fb57  ldarg.0
0x2fb58  ldloc.s  5
0x2fb5a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <CreateUploadSession>d__0::<>u__1
0x2fb5f  ldarg.0
0x2fb60  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <CreateUploadSession>d__0::<>t__builder
0x2fb65  ldloca.s 5
0x2fb67  ldarg.0
0x2fb68  call     T0x2B000111
0x2fb6d  leave    loc_2FC1B
0x2fb72  ldarg.0
0x2fb73  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <CreateUploadSession>d__0::<>u__1
0x2fb78  stloc.s  5
0x2fb7a  ldarg.0
0x2fb7b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <CreateUploadSession>d__0::<>u__1
0x2fb80  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x2fb86  ldarg.0
0x2fb87  ldc.i4.m1
0x2fb88  dup
0x2fb89  stloc.0
0x2fb8a  stfld    int32 <CreateUploadSession>d__0::<>1__state
0x2fb8f  ldloca.s 5
0x2fb91  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x2fb96  stloc.s  4
0x2fb98  ldc.i4   0xC8
0x2fb9d  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x2fba2  dup
0x2fba3  ldloc.1
0x2fba4  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x2fba9  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_RequestMessage(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x2fbae  dup
0x2fbaf  ldloc.s  4
0x2fbb1  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0x2fbb6  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x2fbbb  stloc.2
0x2fbbc  leave.s  loc_2FC07
0x2fbbe  stloc.s  6
0x2fbc0  ldarg.0
0x2fbc1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CreateUploadSession>d__0::<eContext>5__2
0x2fbc6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x2fbcb  ldloc.1
0x2fbcc  ldloc.s  6
0x2fbce  call     instance class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.Crm.Extensibility.StorageService.StorageController::HandleException(class [mscorlib]System.Exception e)
0x2fbd3  stloc.2
0x2fbd4  leave.s  loc_2FC07
0x2fbd6  ldloc.0
0x2fbd7  ldc.i4.0
0x2fbd8  bge.s    loc_2FBED
0x2fbda  ldarg.0
0x2fbdb  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CreateUploadSession>d__0::<eContext>5__2
0x2fbe0  brfalse.s loc_2FBED
0x2fbe2  ldarg.0
0x2fbe3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CreateUploadSession>d__0::<eContext>5__2
0x2fbe8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fbed  endfinally
0x2fbee  stloc.s  7
0x2fbf0  ldarg.0
0x2fbf1  ldc.i4.s 0xFE
0x2fbf3  stfld    int32 <CreateUploadSession>d__0::<>1__state
0x2fbf8  ldarg.0
0x2fbf9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <CreateUploadSession>d__0::<>t__builder
0x2fbfe  ldloc.s  7
0x2fc00  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0x2fc05  leave.s  loc_2FC1B
0x2fc07  ldarg.0
0x2fc08  ldc.i4.s 0xFE
0x2fc0a  stfld    int32 <CreateUploadSession>d__0::<>1__state
0x2fc0f  ldarg.0
0x2fc10  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <CreateUploadSession>d__0::<>t__builder
0x2fc15  ldloc.2
0x2fc16  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0x2fc1b  ret
```
