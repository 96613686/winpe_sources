# Microsoft.Crm.Sdk.Messages.Internal.UpdateUpsertAttributesRequest::get_WizardDataXml

- ea: `0x135b0`
- end: `0x135da`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateUpsertAttributesRequest::get_WizardDataXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x135b0`

## string_xrefs

- `0x135b6`: `WizardDataXml`
- `0x135c8`: `WizardDataXml`

## pseudocode

```c

```

## disassembly

```asm
0x135b0  ldarg.0
0x135b1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x135b6  ldstr    aWizarddataxml_0// "WizardDataXml"
0x135bb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x135c0  brfalse.s loc_135D8
0x135c2  ldarg.0
0x135c3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x135c8  ldstr    aWizarddataxml_0// "WizardDataXml"
0x135cd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x135d2  castclass [mscorlib]System.String
0x135d7  ret
0x135d8  ldnull
0x135d9  ret
```
