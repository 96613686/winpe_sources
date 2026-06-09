# <>c__DisplayClass7_0::<ProcessIndexStatusRequest>b__0

- ea: `0x31020`
- end: `0x310d7`
- name: `<>c__DisplayClass7_0::<ProcessIndexStatusRequest>b__0`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xdc20`
- `0xdc50`
- `0x24ed0`
- `0x31020`

## string_xrefs

- `0x31050`: `prvReadCustomization`

## pseudocode

```c

```

## disassembly

```asm
0x31020  ldarg.0
0x31021  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext <>c__DisplayClass7_0::context
0x31026  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3102b  ldc.i4.0
0x3102c  ldc.i4.0
0x3102d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x31032  stloc.0
0x31033  ldloc.0
0x31034  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0x31039  ldc.i4.0
0x3103a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x3103f  ldloc.0
0x31040  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x31045  ldarg.0
0x31046  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext <>c__DisplayClass7_0::context
0x3104b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x31050  ldstr    aPrvreadcustomi// "prvReadCustomization"
0x31055  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x3105a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x3105f  ldloc.0
0x31060  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31065  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalSearch.ExternalSearchIndexStatusService::.ctor()
0x3106a  stloc.1
0x3106b  ldloc.1
0x3106c  ldloc.0
0x3106d  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalSearch.IndexStatusResponse [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalSearch.ExternalSearchIndexStatusService::RetrieveIndexStatus(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31072  stloc.2
0x31073  ldloc.0
0x31074  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x31079  leave.s  loc_31092
0x3107b  stloc.3
0x3107c  ldloc.0
0x3107d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x31082  ldarg.0
0x31083  ldfld    class Microsoft.Crm.Extensibility.SearchService.IndexesController <>c__DisplayClass7_0::<>4__this
0x31088  ldloc.3
0x31089  call     instance class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.Crm.Extensibility.SearchService.IndexesController::HandleException(class [mscorlib]System.Exception e)
0x3108e  stloc.s  4
0x31090  leave.s  loc_310D4
0x31092  ldloc.2
0x31093  callvirt instance valuetype [System]System.Net.HttpStatusCode [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalSearch.IndexStatusResponse::get_StatusCode()
0x31098  ldc.i4   0xC8
0x3109d  beq.s    loc_310AB
0x3109f  ldloc.2
0x310a0  callvirt instance valuetype [System]System.Net.HttpStatusCode [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalSearch.IndexStatusResponse::get_StatusCode()
0x310a5  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x310aa  throw
0x310ab  ldarg.0
0x310ac  ldfld    class Microsoft.Crm.Extensibility.SearchService.IndexesController <>c__DisplayClass7_0::<>4__this
0x310b1  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x310b6  ldc.i4   0xC8
0x310bb  ldloc.2
0x310bc  call     class [System.Net.Http.Formatting]System.Net.Http.Formatting.JsonMediaTypeFormatter Microsoft.Crm.Extensibility.SearchService.IndexesController::GetJsonFormatter()
0x310c1  call     T0x2B00011E
0x310c6  stloc.s  4
0x310c8  leave.s  loc_310D4
0x310ca  ldloc.0
0x310cb  brfalse.s loc_310D3
0x310cd  ldloc.0
0x310ce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x310d3  endfinally
0x310d4  ldloc.s  4
0x310d6  ret
```
