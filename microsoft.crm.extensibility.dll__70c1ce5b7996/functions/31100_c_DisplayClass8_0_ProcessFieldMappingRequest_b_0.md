# <>c__DisplayClass8_0::<ProcessFieldMappingRequest>b__0

- ea: `0x31100`
- end: `0x3119e`
- name: `<>c__DisplayClass8_0::<ProcessFieldMappingRequest>b__0`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xdc20`
- `0xdc50`
- `0x24ed0`
- `0x31100`

## string_xrefs

- `0x31130`: `prvReadCustomization`

## pseudocode

```c

```

## disassembly

```asm
0x31100  ldarg.0
0x31101  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext <>c__DisplayClass8_0::context
0x31106  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3110b  ldc.i4.0
0x3110c  ldc.i4.0
0x3110d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x31112  stloc.0
0x31113  ldloc.0
0x31114  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0x31119  ldc.i4.0
0x3111a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x3111f  ldloc.0
0x31120  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x31125  ldarg.0
0x31126  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext <>c__DisplayClass8_0::context
0x3112b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x31130  ldstr    aPrvreadcustomi// "prvReadCustomization"
0x31135  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x3113a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x3113f  ldloc.0
0x31140  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31145  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalSearch.ExternalSearchFieldMappingService::.ctor()
0x3114a  stloc.1
0x3114b  ldloc.1
0x3114c  ldloc.0
0x3114d  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalSearch.FieldMappingResponse [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalSearch.ExternalSearchFieldMappingService::RetrieveFieldMapping(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31152  stloc.2
0x31153  ldloc.0
0x31154  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x31159  leave.s  loc_31172
0x3115b  stloc.3
0x3115c  ldloc.0
0x3115d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x31162  ldarg.0
0x31163  ldfld    class Microsoft.Crm.Extensibility.SearchService.IndexesController <>c__DisplayClass8_0::<>4__this
0x31168  ldloc.3
0x31169  call     instance class [System.Net.Http]System.Net.Http.HttpResponseMessage Microsoft.Crm.Extensibility.SearchService.IndexesController::HandleException(class [mscorlib]System.Exception e)
0x3116e  stloc.s  4
0x31170  leave.s  loc_3119B
0x31172  ldarg.0
0x31173  ldfld    class Microsoft.Crm.Extensibility.SearchService.IndexesController <>c__DisplayClass8_0::<>4__this
0x31178  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x3117d  ldc.i4   0xC8
0x31182  ldloc.2
0x31183  call     class [System.Net.Http.Formatting]System.Net.Http.Formatting.JsonMediaTypeFormatter Microsoft.Crm.Extensibility.SearchService.IndexesController::GetJsonFormatter()
0x31188  call     T0x2B00011F
0x3118d  stloc.s  4
0x3118f  leave.s  loc_3119B
0x31191  ldloc.0
0x31192  brfalse.s loc_3119A
0x31194  ldloc.0
0x31195  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3119a  endfinally
0x3119b  ldloc.s  4
0x3119d  ret
```
