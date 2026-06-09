# Microsoft.Crm.Sdk.Messages.Internal.GetFieldAndPropertiesXmlResponse::get_FieldAndPropertiesXml

- ea: `0x144f0`
- end: `0x1451a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetFieldAndPropertiesXmlResponse::get_FieldAndPropertiesXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x144f0`

## string_xrefs

- `0x144f6`: `FieldAndPropertiesXml`
- `0x14508`: `FieldAndPropertiesXml`

## pseudocode

```c

```

## disassembly

```asm
0x144f0  ldarg.0
0x144f1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x144f6  ldstr    aFieldandproper// "FieldAndPropertiesXml"
0x144fb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14500  brfalse.s loc_14518
0x14502  ldarg.0
0x14503  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x14508  ldstr    aFieldandproper// "FieldAndPropertiesXml"
0x1450d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14512  castclass [mscorlib]System.String
0x14517  ret
0x14518  ldnull
0x14519  ret
```
