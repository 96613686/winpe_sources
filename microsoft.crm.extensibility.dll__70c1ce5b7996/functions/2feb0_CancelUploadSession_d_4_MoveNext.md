# <CancelUploadSession>d__4::MoveNext

- ea: `0x2feb0`
- end: `0x30027`
- name: `<CancelUploadSession>d__4::MoveNext`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xd040`
- `0xd200`
- `0x24ed0`
- `0x2feb0`

## string_xrefs

- `0x2ff03`: `prvCreateEntity`

## pseudocode

```c

```

## disassembly

```asm
0x2feb0  ldarg.0
0x2feb1  ldfld    int32 <CancelUploadSession>d__4::<>1__state
0x2feb6  stloc.0
0x2feb7  ldarg.0
0x2feb8  ldfld    class Microsoft.Crm.Extensibility.StorageService.StorageController <CancelUploadSession>d__4::<>4__this
0x2febd  stloc.1
0x2febe  ldloc.0
0x2febf  brfalse.s loc_2FED7
0x2fec1  ldloc.1
0x2fec2  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x2fec7  ldc.i4   0x1F5
0x2fecc  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Net.Http.Formatting]System.Net.Http.HttpRequestMessageExtensions::CreateResponse(class [System.Net.Http]System.Net.Http.HttpRequestMessage, valuetype [System]System.Net.HttpStatusCode)
0x2fed1  stloc.2
0x2fed2  leave    loc_30012
0x2fed7  nop
0x2fed8  ldloc.0
0x2fed9  pop
0x2feda  nop
0x2fedb  ldloc.0
0x2fedc  brfalse  loc_2FF73
0x2fee1  ldarg.0
0x2fee2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CancelUploadSession>d__4::<eContext>5__2
0x2fee7  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0x2feec  ldc.i4.0
0x2feed  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x2fef2  ldarg.0
0x2fef3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CancelUploadSession>d__4::<eContext>5__2
0x2fef8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x2fefd  ldloc.3
0x2fefe  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2ff03  ldstr    aPrvcreateentit// "prvCreateEntity"
0x2ff08  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x2ff0d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x2ff12  ldarg.0
0x2ff13  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CancelUploadSession>d__4::<eContext>5__2
0x2ff18  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2ff1d  ldarg.0
0x2ff1e  ldfld    class Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata <CancelUploadSession>d__4::metadata
0x2ff23  callvirt instance string Microsoft.Crm.Extensibility.StorageService.EndUploadSessionRequestMetadata::get_SasURI()
0x2ff28  newobj   instance void [System]System.Uri::.ctor(string)
0x2ff2d  call     instance string[] [System]System.Uri::get_Segments()
0x2ff32  ldc.i4.2
0x2ff33  ldelem.ref
0x2ff34  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2ff39  ldloc.3
0x2ff3a  call     class [mscorlib]System.Threading.Tasks.Task`1<bool> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalStorage.UploadService::CancelUploadSession(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext)
0x2ff3f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x2ff44  stloc.s  4
0x2ff46  ldloca.s 4
0x2ff48  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x2ff4d  brtrue.s loc_2FF90
0x2ff4f  ldarg.0
0x2ff50  ldc.i4.0
0x2ff51  dup
0x2ff52  stloc.0
0x2ff53  stfld    int32 <CancelUploadSession>d__4::<>1__state
0x2ff58  ldarg.0
0x2ff59  ldloc.s  4
0x2ff5b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <CancelUploadSession>d__4::<>u__1
0x2ff60  ldarg.0
0x2ff61  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <CancelUploadSession>d__4::<>t__builder
0x2ff66  ldloca.s 4
0x2ff68  ldarg.0
0x2ff69  call     T0x2B000114
0x2ff6e  leave    loc_30026
0x2ff73  ldarg.0
0x2ff74  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <CancelUploadSession>d__4::<>u__1
0x2ff79  stloc.s  4
0x2ff7b  ldarg.0
0x2ff7c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <CancelUploadSession>d__4::<>u__1
0x2ff81  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x2ff87  ldarg.0
0x2ff88  ldc.i4.m1
0x2ff89  dup
0x2ff8a  stloc.0
0x2ff8b  stfld    int32 <CancelUploadSession>d__4::<>1__state
0x2ff90  ldloca.s 4
0x2ff92  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x2ff97  brfalse.s loc_2FFB1
0x2ff99  ldloc.1
0x2ff9a  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x2ff9f  ldc.i4   0xC8
0x2ffa4  ldstr    aAllUploadSessi// "All upload sessions cleared."
0x2ffa9  call     T0x2B000115
0x2ffae  stloc.2
0x2ffaf  leave.s  loc_30012
0x2ffb1  ldloc.1
0x2ffb2  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x2ffb7  ldc.i4   0x1F4
0x2ffbc  ldstr    aUnableToClearA// "Unable to clear all upload sessions."
0x2ffc1  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::CreateErrorResponse(class [System.Net.Http]System.Net.Http.HttpRequestMessage, valuetype [System]System.Net.HttpStatusCode, string)
0x2ffc6  stloc.2
0x2ffc7  leave.s  loc_30012
0x2ffc9  stloc.s  5
0x2ffcb  ldarg.0
0x2ffcc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CancelUploadSession>d__4::<eContext>5__2
0x2ffd1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x2ffd6  ldloc.1
0x2ffd7  ldloc.s  5
0x2ffd9  call     instance class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.Crm.Extensibility.StorageService.StorageController::HandleException(class [mscorlib]System.Exception e)
0x2ffde  stloc.2
0x2ffdf  leave.s  loc_30012
0x2ffe1  ldloc.0
0x2ffe2  ldc.i4.0
0x2ffe3  bge.s    loc_2FFF8
0x2ffe5  ldarg.0
0x2ffe6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CancelUploadSession>d__4::<eContext>5__2
0x2ffeb  brfalse.s loc_2FFF8
0x2ffed  ldarg.0
0x2ffee  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <CancelUploadSession>d__4::<eContext>5__2
0x2fff3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2fff8  endfinally
0x2fff9  stloc.s  6
0x2fffb  ldarg.0
0x2fffc  ldc.i4.s 0xFE
0x2fffe  stfld    int32 <CancelUploadSession>d__4::<>1__state
0x30003  ldarg.0
0x30004  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <CancelUploadSession>d__4::<>t__builder
0x30009  ldloc.s  6
0x3000b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0x30010  leave.s  loc_30026
0x30012  ldarg.0
0x30013  ldc.i4.s 0xFE
0x30015  stfld    int32 <CancelUploadSession>d__4::<>1__state
0x3001a  ldarg.0
0x3001b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <CancelUploadSession>d__4::<>t__builder
0x30020  ldloc.2
0x30021  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0x30026  ret
```
