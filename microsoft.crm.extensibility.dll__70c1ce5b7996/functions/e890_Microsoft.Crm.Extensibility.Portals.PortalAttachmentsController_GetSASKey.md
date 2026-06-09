# Microsoft.Crm.Extensibility.Portals.PortalAttachmentsController::GetSASKey

- ea: `0xe890`
- end: `0xe99b`
- name: `Microsoft.Crm.Extensibility.Portals.PortalAttachmentsController::GetSASKey`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xd9b0`
- `0xe890`
- `0xe9a0`
- `0xe9d0`
- `0x24ed0`
- `0x24f30`

## string_xrefs

- `0xe91f`: `Only the System User can access this endpoint.`

## pseudocode

```c

```

## disassembly

```asm
0xe890  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0xe895  stloc.0
0xe896  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xe89b  stloc.1
0xe89c  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetOrganizationContext()
0xe8a1  stloc.2
0xe8a2  ldarg.0
0xe8a3  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0xe8a8  ldloc.2
0xe8a9  call     string Microsoft.Crm.Extensibility.SearchService.SearchIndexUtilities::ValidateVersionInformation(class [System.Net.Http]System.Net.Http.HttpRequestMessage requestMessage, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0xe8ae  pop
0xe8af  leave.s  loc_E8E9
0xe8b1  stloc.s  5
0xe8b3  ldc.i4   0x190
0xe8b8  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xe8bd  dup
0xe8be  ldstr    aValidApiVersio// "Valid API version not sent. \nException"...
0xe8c3  ldloc.s  5
0xe8c5  ldloc.s  5
0xe8c7  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0xe8cc  ldloc.s  5
0xe8ce  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0xe8d3  call     string [mscorlib]System.String::Format(string, object, object, object)
0xe8d8  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0xe8dd  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0xe8e2  stloc.s  6
0xe8e4  leave    loc_E998
0xe8e9  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0xe8ee  stloc.3
0xe8ef  ldloc.2
0xe8f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xe8f5  ldc.i4.0
0xe8f6  ldc.i4.0
0xe8f7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xe8fc  stloc.s  7
0xe8fe  ldloc.s  7
0xe900  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0xe905  ldc.i4.0
0xe906  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0xe90b  ldloc.s  7
0xe90d  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_IsImpersonatingSystemUser()
0xe912  brtrue.s loc_E932
0xe914  ldc.i4   0x193
0xe919  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor(valuetype [System]System.Net.HttpStatusCode)
0xe91e  dup
0xe91f  ldstr    aOnlyTheSystemU// "Only the System User can access this en"...
0xe924  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0xe929  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0xe92e  stloc.s  6
0xe930  leave.s  loc_E998
0xe932  nop
0xe933  ldloc.2
0xe934  ldloc.1
0xe935  ldloc.3
0xe936  ldarg.1
0xe937  call     class [System.Net.Http]System.Net.Http.HttpResponseMessage [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Portals.PortalsAttachmentProvider::ProcessGetSasKeyRequest(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xe93c  stloc.s  4
0xe93e  ldloc.s  7
0xe940  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0xe945  leave.s  loc_E95C
0xe947  stloc.s  8
0xe949  ldloc.s  7
0xe94b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0xe950  ldarg.0
0xe951  ldloc.s  8
0xe953  call     instance class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.Crm.Extensibility.Portals.PortalAttachmentsController::HandleException(class [mscorlib]System.Exception ex)
0xe958  stloc.s  4
0xe95a  leave.s  loc_E95C
0xe95c  ldarg.0
0xe95d  ldloc.s  4
0xe95f  ldloc.0
0xe960  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xe965  stloc.s  9
0xe967  ldloca.s 9
0xe969  call     instance string [mscorlib]System.Int64::ToString()
0xe96e  ldloca.s 1
0xe970  constrained. [mscorlib]System.Guid
0xe976  callvirt instance string [mscorlib]System.Object::ToString()
0xe97b  call     instance void Microsoft.Crm.Extensibility.Portals.PortalAttachmentsController::SetResponseHeaders(class [System.Net.Http]System.Net.Http.HttpResponseMessage responseMessage, string elapsedTime, string correlationId)
0xe980  ldloc.0
0xe981  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xe986  ldloc.s  4
0xe988  stloc.s  6
0xe98a  leave.s  loc_E998
0xe98c  ldloc.s  7
0xe98e  brfalse.s loc_E997
0xe990  ldloc.s  7
0xe992  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe997  endfinally
0xe998  ldloc.s  6
0xe99a  ret
```
