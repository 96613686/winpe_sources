# Microsoft.Crm.Sdk.Messages.Internal.UploadMapXmlRequest::get_mapXml

- ea: `0x13740`
- end: `0x1376a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UploadMapXmlRequest::get_mapXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x13740`

## string_xrefs

- `0x13746`: `mapXml`
- `0x13758`: `mapXml`

## pseudocode

```c

```

## disassembly

```asm
0x13740  ldarg.0
0x13741  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x13746  ldstr    aMapxml_0// "mapXml"
0x1374b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x13750  brfalse.s loc_13768
0x13752  ldarg.0
0x13753  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x13758  ldstr    aMapxml_0// "mapXml"
0x1375d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x13762  castclass [mscorlib]System.String
0x13767  ret
0x13768  ldnull
0x13769  ret
```
