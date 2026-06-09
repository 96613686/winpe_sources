# Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::Update_0

- ea: `0x24d00`
- end: `0x24da4`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::Update_0`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1e480`
- `0x24c10`

## callees

- `0xa610`
- `0x192a0`
- `0x19a80`
- `0x24b60`
- `0x24d00`
- `0x24db0`
- `0x24e50`
- `0x24e60`

## string_xrefs

- `0x24d2f`: `RecordCreated`

## pseudocode

```c

```

## disassembly

```asm
0x24d00  ldc.i4.0
0x24d01  stloc.0
0x24d02  ldarg.2
0x24d03  switch   loc_24D1A, loc_24D49, loc_24D72, loc_24D22
0x24d18  br.s     loc_24D79
0x24d1a  ldarg.0
0x24d1b  ldarg.1
0x24d1c  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::CreateOrganizationResponse(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x24d21  ret
0x24d22  ldarg.0
0x24d23  ldarg.1
0x24d24  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::Upsert(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x24d29  dup
0x24d2a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x24d2f  ldstr    aRecordcreated// "RecordCreated"
0x24d34  ldloca.s 1
0x24d36  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::TryGetValue(var<u1>, !!T0)
0x24d3b  pop
0x24d3c  ldarg.0
0x24d3d  ldloc.1
0x24d3e  unbox.any [mscorlib]System.Boolean
0x24d43  stfld    bool Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::_isRecordCreatedFromUpsertOperation
0x24d48  ret
0x24d49  ldc.i4.1
0x24d4a  stloc.0
0x24d4b  ldarg.1
0x24d4c  ldarg.0
0x24d4d  call     instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x24d52  callvirt instance class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_IfMatch()
0x24d57  callvirt instance string [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue::get_Tag()
0x24d5c  ldstr    asc_3F98A// "\""
0x24d61  ldstr    asc_39E2A// ""
0x24d66  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x24d6b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_RowVersion(string)
0x24d70  br.s     loc_24D79
0x24d72  ldarg.0
0x24d73  ldc.i4.1
0x24d74  stfld    bool Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::_isUpdateOperation
0x24d79  ldarg.1
0x24d7a  ldarg.0
0x24d7b  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_CrmExecutionContext()
0x24d80  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CorrelationToken()
0x24d85  ldarg.0
0x24d86  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_CrmExecutionContext()
0x24d8b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerOriginToken()
0x24d90  ldc.i4.0
0x24d91  ldc.i4.1
0x24d92  ldloc.0
0x24d93  ldarg.0
0x24d94  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::_headers
0x24d99  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataOptionalParameters()
0x24d9e  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateResponse Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken callerOriginToken, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType serviceType, bool checkAdminMode, [opt] bool checkForOptimisticConcurrency, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> optionalParameters)
0x24da3  ret
```
