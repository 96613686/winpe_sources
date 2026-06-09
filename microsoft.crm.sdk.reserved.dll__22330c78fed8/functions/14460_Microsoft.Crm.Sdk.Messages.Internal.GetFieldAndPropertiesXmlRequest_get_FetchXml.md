# Microsoft.Crm.Sdk.Messages.Internal.GetFieldAndPropertiesXmlRequest::get_FetchXml

- ea: `0x14460`
- end: `0x1448a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetFieldAndPropertiesXmlRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14460`

## string_xrefs

- `0x14466`: `FetchXml`
- `0x14478`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x14460  ldarg.0
0x14461  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14466  ldstr    aFetchxml// "FetchXml"
0x1446b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14470  brfalse.s loc_14488
0x14472  ldarg.0
0x14473  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x14478  ldstr    aFetchxml// "FetchXml"
0x1447d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14482  castclass [mscorlib]System.String
0x14487  ret
0x14488  ldnull
0x14489  ret
```
