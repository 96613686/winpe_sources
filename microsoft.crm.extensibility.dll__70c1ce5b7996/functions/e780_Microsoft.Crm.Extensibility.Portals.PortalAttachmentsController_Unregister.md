# Microsoft.Crm.Extensibility.Portals.PortalAttachmentsController::Unregister

- ea: `0xe780`
- end: `0xe88b`
- name: `Microsoft.Crm.Extensibility.Portals.PortalAttachmentsController::Unregister`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xd9b0`
- `0xe780`
- `0xe9a0`
- `0xe9d0`
- `0x24ed0`
- `0x24f30`

## string_xrefs

- `0xe80f`: `Only the System User can access this endpoint.`

## pseudocode

```c

```

## disassembly

```asm
0xe780  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xe785  stloc.0
0xe786  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xe78b  stloc.1
0xe78c  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetOrganizationContext()
0xe791  stloc.2
0xe792  ldarg.0
0xe793  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0xe798  ldloc.2
0xe799  call     string Microsoft.Crm.Extensibility.SearchService.SearchIndexUtilities::ValidateVersionInformation(class [System.Net.Http]System.Net.Http.HttpRequestMessage requestMessage, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xe79e  pop
0xe79f  leave.s  loc_E7D9
0xe7a1  stloc.s  5
0xe7a3  ldc.i4   0x190
0xe7a8  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xe7ad  dup
0xe7ae  ldstr    aValidApiVersio// "Valid API version not sent. \nException"...
0xe7b3  ldloc.s  5
0xe7b5  ldloc.s  5
0xe7b7  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xe7bc  ldloc.s  5
0xe7be  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0xe7c3  call     string [mscorlib]System.String::Format(string, object, object, object)
0xe7c8  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0xe7cd  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0xe7d2  stloc.s  6
0xe7d4  leave    loc_E888
0xe7d9  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0xe7de  stloc.3
0xe7df  ldloc.2
0xe7e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xe7e5  ldc.i4.0
0xe7e6  ldc.i4.0
0xe7e7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xe7ec  stloc.s  7
0xe7ee  ldloc.s  7
0xe7f0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0xe7f5  ldc.i4.0
0xe7f6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0xe7fb  ldloc.s  7
0xe7fd  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_IsImpersonatingSystemUser()
0xe802  brtrue.s loc_E822
0xe804  ldc.i4   0x193
0xe809  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xe80e  dup
0xe80f  ldstr    aOnlyTheSystemU// "Only the System User can access this en"...
0xe814  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0xe819  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0xe81e  stloc.s  6
0xe820  leave.s  loc_E888
0xe822  nop
0xe823  ldloc.2
0xe824  ldloc.1
0xe825  ldloc.3
0xe826  ldarg.1
0xe827  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Portals.PortalsAttachmentProvider::ProcessPortalsUnregistrationRequest(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xe82c  stloc.s  4
0xe82e  ldloc.s  7
0xe830  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0xe835  leave.s  loc_E84C
0xe837  stloc.s  8
0xe839  ldloc.s  7
0xe83b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0xe840  ldarg.0
0xe841  ldloc.s  8
0xe843  call     instance class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.Crm.Extensibility.Portals.PortalAttachmentsController::HandleException(class [mscorlib]System.Exception ex)
0xe848  stloc.s  4
0xe84a  leave.s  loc_E84C
0xe84c  ldarg.0
0xe84d  ldloc.s  4
0xe84f  ldloc.0
0xe850  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xe855  stloc.s  9
0xe857  ldloca.s 9
0xe859  call     instance string [mscorlib]System.Int64::ToString()
0xe85e  ldloca.s 1
0xe860  constrained. [mscorlib]System.Guid
0xe866  callvirt instance string [mscorlib]System.Object::ToString()
0xe86b  call     instance void Microsoft.Crm.Extensibility.Portals.PortalAttachmentsController::SetResponseHeaders(class [System.Net.Http]System.Net.Http.HttpResponseMessage responseMessage, string elapsedTime, string correlationId)
0xe870  ldloc.0
0xe871  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xe876  ldloc.s  4
0xe878  stloc.s  6
0xe87a  leave.s  loc_E888
0xe87c  ldloc.s  7
0xe87e  brfalse.s loc_E887
0xe880  ldloc.s  7
0xe882  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe887  endfinally
0xe888  ldloc.s  6
0xe88a  ret
```
