# Microsoft.Crm.Sdk.Messages.Internal.RenderTemplateRequest::get_FetchXml

- ea: `0x5430`
- end: `0x545a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RenderTemplateRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5430`

## string_xrefs

- `0x5436`: `FetchXml`
- `0x5448`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x5430  ldarg.0
0x5431  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5436  ldstr    aFetchxml// "FetchXml"
0x543b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x5440  brfalse.s loc_5458
0x5442  ldarg.0
0x5443  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5448  ldstr    aFetchxml// "FetchXml"
0x544d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x5452  castclass [mscorlib]System.String
0x5457  ret
0x5458  ldnull
0x5459  ret
```
