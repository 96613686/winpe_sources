# Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::get_ActivityXml

- ea: `0x15bc0`
- end: `0x15bea`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateMiniCampaignRequest::get_ActivityXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x15bc0`

## string_xrefs

- `0x15bc6`: `ActivityXml`
- `0x15bd8`: `ActivityXml`

## pseudocode

```c

```

## disassembly

```asm
0x15bc0  ldarg.0
0x15bc1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x15bc6  ldstr    aActivityxml// "ActivityXml"
0x15bcb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x15bd0  brfalse.s loc_15BE8
0x15bd2  ldarg.0
0x15bd3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x15bd8  ldstr    aActivityxml// "ActivityXml"
0x15bdd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x15be2  castclass [mscorlib]System.String
0x15be7  ret
0x15be8  ldnull
0x15be9  ret
```
