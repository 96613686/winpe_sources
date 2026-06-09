# Microsoft.Crm.Asynchronous.BulkDetectDuplicatesOperation::GetQueryExpressionFromFetchXml

- ea: `0x3260`
- end: `0x328b`
- name: `Microsoft.Crm.Asynchronous.BulkDetectDuplicatesOperation::GetQueryExpressionFromFetchXml`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x32c0`

## callees

- `0x3260`

## pseudocode

```c

```

## disassembly

```asm
0x3260  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.FetchXmlToQueryExpressionRequest::.ctor()
0x3265  stloc.0
0x3266  ldloc.0
0x3267  ldarg.1
0x3268  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.FetchXmlToQueryExpressionRequest::set_FetchXml(string)
0x326d  ldarg.0
0x326e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDetectDuplicatesOperation::_crmServiceSystem
0x3273  ldloc.0
0x3274  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x3279  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.FetchXmlToQueryExpressionResponse
0x327e  stloc.1
0x327f  ldloc.1
0x3280  brtrue.s loc_3284
0x3282  ldnull
0x3283  ret
0x3284  ldloc.1
0x3285  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.FetchXmlToQueryExpressionResponse::get_Query()
0x328a  ret
```
