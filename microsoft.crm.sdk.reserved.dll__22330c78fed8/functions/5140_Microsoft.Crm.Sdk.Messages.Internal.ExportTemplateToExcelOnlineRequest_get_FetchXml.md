# Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineRequest::get_FetchXml

- ea: `0x5140`
- end: `0x516a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5140`

## string_xrefs

- `0x5146`: `FetchXml`
- `0x5158`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x5140  ldarg.0
0x5141  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5146  ldstr    aFetchxml// "FetchXml"
0x514b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x5150  brfalse.s loc_5168
0x5152  ldarg.0
0x5153  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5158  ldstr    aFetchxml// "FetchXml"
0x515d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x5162  castclass [mscorlib]System.String
0x5167  ret
0x5168  ldnull
0x5169  ret
```
