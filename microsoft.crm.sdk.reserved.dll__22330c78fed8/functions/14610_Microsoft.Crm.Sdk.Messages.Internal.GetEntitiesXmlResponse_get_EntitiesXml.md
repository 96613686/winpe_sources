# Microsoft.Crm.Sdk.Messages.Internal.GetEntitiesXmlResponse::get_EntitiesXml

- ea: `0x14610`
- end: `0x1463a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetEntitiesXmlResponse::get_EntitiesXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14610`

## string_xrefs

- `0x14616`: `EntitiesXml`
- `0x14628`: `EntitiesXml`

## pseudocode

```c

```

## disassembly

```asm
0x14610  ldarg.0
0x14611  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x14616  ldstr    aEntitiesxml// "EntitiesXml"
0x1461b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14620  brfalse.s loc_14638
0x14622  ldarg.0
0x14623  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x14628  ldstr    aEntitiesxml// "EntitiesXml"
0x1462d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14632  castclass [mscorlib]System.String
0x14637  ret
0x14638  ldnull
0x14639  ret
```
