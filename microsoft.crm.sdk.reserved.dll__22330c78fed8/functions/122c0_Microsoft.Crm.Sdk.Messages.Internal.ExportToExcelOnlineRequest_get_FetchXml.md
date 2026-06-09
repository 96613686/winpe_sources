# Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelOnlineRequest::get_FetchXml

- ea: `0x122c0`
- end: `0x122ea`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelOnlineRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x122c0`

## string_xrefs

- `0x122c6`: `FetchXml`
- `0x122d8`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x122c0  ldarg.0
0x122c1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x122c6  ldstr    aFetchxml// "FetchXml"
0x122cb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x122d0  brfalse.s loc_122E8
0x122d2  ldarg.0
0x122d3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x122d8  ldstr    aFetchxml// "FetchXml"
0x122dd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x122e2  castclass [mscorlib]System.String
0x122e7  ret
0x122e8  ldnull
0x122e9  ret
```
