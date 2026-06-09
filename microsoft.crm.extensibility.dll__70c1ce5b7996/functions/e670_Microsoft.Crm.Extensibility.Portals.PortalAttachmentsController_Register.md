# Microsoft.Crm.Extensibility.Portals.PortalAttachmentsController::Register

- ea: `0xe670`
- end: `0xe77b`
- name: `Microsoft.Crm.Extensibility.Portals.PortalAttachmentsController::Register`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xd9b0`
- `0xe670`
- `0xe9a0`
- `0xe9d0`
- `0x24ed0`
- `0x24f30`

## string_xrefs

- `0xe6ff`: `Only the System User can access this endpoint.`

## pseudocode

```c

```

## disassembly

```asm
0xe670  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xe675  stloc.0
0xe676  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xe67b  stloc.1
0xe67c  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetOrganizationContext()
0xe681  stloc.2
0xe682  ldarg.0
0xe683  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0xe688  ldloc.2
0xe689  call     string Microsoft.Crm.Extensibility.SearchService.SearchIndexUtilities::ValidateVersionInformation(class [System.Net.Http]System.Net.Http.HttpRequestMessage requestMessage, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xe68e  pop
0xe68f  leave.s  loc_E6C9
0xe691  stloc.s  5
0xe693  ldc.i4   0x190
0xe698  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xe69d  dup
0xe69e  ldstr    aValidApiVersio// "Valid API version not sent. \nException"...
0xe6a3  ldloc.s  5
0xe6a5  ldloc.s  5
0xe6a7  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xe6ac  ldloc.s  5
0xe6ae  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0xe6b3  call     string [mscorlib]System.String::Format(string, object, object, object)
0xe6b8  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0xe6bd  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0xe6c2  stloc.s  6
0xe6c4  leave    loc_E778
0xe6c9  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0xe6ce  stloc.3
0xe6cf  ldloc.2
0xe6d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xe6d5  ldc.i4.0
0xe6d6  ldc.i4.0
0xe6d7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xe6dc  stloc.s  7
0xe6de  ldloc.s  7
0xe6e0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0xe6e5  ldc.i4.0
0xe6e6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0xe6eb  ldloc.s  7
0xe6ed  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_IsImpersonatingSystemUser()
0xe6f2  brtrue.s loc_E712
0xe6f4  ldc.i4   0x193
0xe6f9  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xe6fe  dup
0xe6ff  ldstr    aOnlyTheSystemU// "Only the System User can access this en"...
0xe704  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0xe709  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0xe70e  stloc.s  6
0xe710  leave.s  loc_E778
0xe712  nop
0xe713  ldloc.2
0xe714  ldloc.1
0xe715  ldloc.3
0xe716  ldarg.1
0xe717  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Portals.PortalsAttachmentProvider::ProcessPortalsRegistrationRequest(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xe71c  stloc.s  4
0xe71e  ldloc.s  7
0xe720  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0xe725  leave.s  loc_E73C
0xe727  stloc.s  8
0xe729  ldloc.s  7
0xe72b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0xe730  ldarg.0
0xe731  ldloc.s  8
0xe733  call     instance class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.Crm.Extensibility.Portals.PortalAttachmentsController::HandleException(class [mscorlib]System.Exception ex)
0xe738  stloc.s  4
0xe73a  leave.s  loc_E73C
0xe73c  ldarg.0
0xe73d  ldloc.s  4
0xe73f  ldloc.0
0xe740  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xe745  stloc.s  9
0xe747  ldloca.s 9
0xe749  call     instance string [mscorlib]System.Int64::ToString()
0xe74e  ldloca.s 1
0xe750  constrained. [mscorlib]System.Guid
0xe756  callvirt instance string [mscorlib]System.Object::ToString()
0xe75b  call     instance void Microsoft.Crm.Extensibility.Portals.PortalAttachmentsController::SetResponseHeaders(class [System.Net.Http]System.Net.Http.HttpResponseMessage responseMessage, string elapsedTime, string correlationId)
0xe760  ldloc.0
0xe761  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xe766  ldloc.s  4
0xe768  stloc.s  6
0xe76a  leave.s  loc_E778
0xe76c  ldloc.s  7
0xe76e  brfalse.s loc_E777
0xe770  ldloc.s  7
0xe772  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe777  endfinally
0xe778  ldloc.s  6
0xe77a  ret
```
