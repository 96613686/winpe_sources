# Microsoft.Crm.Sdk.Messages.Internal.GetImportWizardXmlResponse::get_ImportWizardXml

- ea: `0x5f70`
- end: `0x5f9a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetImportWizardXmlResponse::get_ImportWizardXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5f70`

## string_xrefs

- `0x5f76`: `ImportWizardXml`
- `0x5f88`: `ImportWizardXml`

## pseudocode

```c

```

## disassembly

```asm
0x5f70  ldarg.0
0x5f71  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x5f76  ldstr    aImportwizardxm// "ImportWizardXml"
0x5f7b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x5f80  brfalse.s loc_5F98
0x5f82  ldarg.0
0x5f83  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x5f88  ldstr    aImportwizardxm// "ImportWizardXml"
0x5f8d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x5f92  castclass [mscorlib]System.String
0x5f97  ret
0x5f98  ldnull
0x5f99  ret
```
