# Microsoft.Crm.Sdk.Messages.Internal.AddMembersByFetchXmlListRequest::get_FetchXml

- ea: `0x15330`
- end: `0x1535a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.AddMembersByFetchXmlListRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x15330`

## string_xrefs

- `0x15336`: `FetchXml`
- `0x15348`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x15330  ldarg.0
0x15331  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x15336  ldstr    aFetchxml// "FetchXml"
0x1533b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x15340  brfalse.s loc_15358
0x15342  ldarg.0
0x15343  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x15348  ldstr    aFetchxml// "FetchXml"
0x1534d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x15352  castclass [mscorlib]System.String
0x15357  ret
0x15358  ldnull
0x15359  ret
```
