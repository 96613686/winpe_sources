# Microsoft.Crm.Sdk.Messages.Internal.RemoveMembersByFetchXmlListRequest::get_FetchXml

- ea: `0x165b0`
- end: `0x165da`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RemoveMembersByFetchXmlListRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x165b0`

## string_xrefs

- `0x165b6`: `FetchXml`
- `0x165c8`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x165b0  ldarg.0
0x165b1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x165b6  ldstr    aFetchxml// "FetchXml"
0x165bb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x165c0  brfalse.s loc_165D8
0x165c2  ldarg.0
0x165c3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x165c8  ldstr    aFetchxml// "FetchXml"
0x165cd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x165d2  castclass [mscorlib]System.String
0x165d7  ret
0x165d8  ldnull
0x165d9  ret
```
