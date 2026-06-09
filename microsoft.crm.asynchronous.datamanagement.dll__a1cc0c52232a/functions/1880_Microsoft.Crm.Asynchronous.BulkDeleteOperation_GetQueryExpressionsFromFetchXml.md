# Microsoft.Crm.Asynchronous.BulkDeleteOperation::GetQueryExpressionsFromFetchXml

- ea: `0x1880`
- end: `0x18c5`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::GetQueryExpressionsFromFetchXml`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f350`

## callees

- `0x1880`

## pseudocode

```c

```

## disassembly

```asm
0x1880  ldarg.1
0x1881  ldlen
0x1882  conv.i4
0x1883  newarr   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression
0x1888  stloc.0
0x1889  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.FetchXmlToQueryExpressionRequest::.ctor()
0x188e  stloc.1
0x188f  ldnull
0x1890  stloc.2
0x1891  ldc.i4.0
0x1892  stloc.3
0x1893  br.s     loc_18BD
0x1895  ldloc.1
0x1896  ldarg.1
0x1897  ldloc.3
0x1898  ldelem.ref
0x1899  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.FetchXmlToQueryExpressionRequest::set_FetchXml(string)
0x189e  ldarg.0
0x189f  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.BulkDeleteOperation::_crmService
0x18a4  ldloc.1
0x18a5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x18aa  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.FetchXmlToQueryExpressionResponse
0x18af  stloc.2
0x18b0  ldloc.0
0x18b1  ldloc.3
0x18b2  ldloc.2
0x18b3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.FetchXmlToQueryExpressionResponse::get_Query()
0x18b8  stelem.ref
0x18b9  ldloc.3
0x18ba  ldc.i4.1
0x18bb  add
0x18bc  stloc.3
0x18bd  ldloc.3
0x18be  ldarg.1
0x18bf  ldlen
0x18c0  conv.i4
0x18c1  blt.s    loc_1895
0x18c3  ldloc.0
0x18c4  ret
```
