# Microsoft.Crm.Sdk.Messages.Internal.RetrieveReportSqlFromQueryRequest::get_FetchXml

- ea: `0x8da0`
- end: `0x8dca`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveReportSqlFromQueryRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8da0`

## string_xrefs

- `0x8da6`: `FetchXml`
- `0x8db8`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x8da0  ldarg.0
0x8da1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8da6  ldstr    aFetchxml// "FetchXml"
0x8dab  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x8db0  brfalse.s loc_8DC8
0x8db2  ldarg.0
0x8db3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8db8  ldstr    aFetchxml// "FetchXml"
0x8dbd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x8dc2  castclass [mscorlib]System.String
0x8dc7  ret
0x8dc8  ldnull
0x8dc9  ret
```
