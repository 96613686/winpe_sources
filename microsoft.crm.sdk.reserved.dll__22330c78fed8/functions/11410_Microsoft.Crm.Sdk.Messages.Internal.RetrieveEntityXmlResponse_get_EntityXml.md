# Microsoft.Crm.Sdk.Messages.Internal.RetrieveEntityXmlResponse::get_EntityXml

- ea: `0x11410`
- end: `0x1143a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveEntityXmlResponse::get_EntityXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11410`

## string_xrefs

- `0x11416`: `EntityXml`
- `0x11428`: `EntityXml`

## pseudocode

```c

```

## disassembly

```asm
0x11410  ldarg.0
0x11411  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11416  ldstr    aEntityxml// "EntityXml"
0x1141b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11420  brfalse.s loc_11438
0x11422  ldarg.0
0x11423  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11428  ldstr    aEntityxml// "EntityXml"
0x1142d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11432  castclass [mscorlib]System.String
0x11437  ret
0x11438  ldnull
0x11439  ret
```
