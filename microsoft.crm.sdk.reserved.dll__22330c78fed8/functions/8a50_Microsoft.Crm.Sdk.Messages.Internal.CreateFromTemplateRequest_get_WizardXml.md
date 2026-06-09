# Microsoft.Crm.Sdk.Messages.Internal.CreateFromTemplateRequest::get_WizardXml

- ea: `0x8a50`
- end: `0x8a7a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateFromTemplateRequest::get_WizardXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8a50`

## string_xrefs

- `0x8a56`: `WizardXml`
- `0x8a68`: `WizardXml`

## pseudocode

```c

```

## disassembly

```asm
0x8a50  ldarg.0
0x8a51  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8a56  ldstr    aWizardxml// "WizardXml"
0x8a5b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x8a60  brfalse.s loc_8A78
0x8a62  ldarg.0
0x8a63  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8a68  ldstr    aWizardxml// "WizardXml"
0x8a6d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x8a72  castclass [mscorlib]System.String
0x8a77  ret
0x8a78  ldnull
0x8a79  ret
```
