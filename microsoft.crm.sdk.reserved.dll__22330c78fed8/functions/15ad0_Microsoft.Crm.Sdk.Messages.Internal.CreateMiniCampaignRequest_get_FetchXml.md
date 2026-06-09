# Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::get_FetchXml

- ea: `0x15ad0`
- end: `0x15afa`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x15ad0`

## string_xrefs

- `0x15ad6`: `FetchXml`
- `0x15ae8`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x15ad0  ldarg.0
0x15ad1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x15ad6  ldstr    aFetchxml// "FetchXml"
0x15adb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x15ae0  brfalse.s loc_15AF8
0x15ae2  ldarg.0
0x15ae3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x15ae8  ldstr    aFetchxml// "FetchXml"
0x15aed  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x15af2  castclass [mscorlib]System.String
0x15af7  ret
0x15af8  ldnull
0x15af9  ret
```
