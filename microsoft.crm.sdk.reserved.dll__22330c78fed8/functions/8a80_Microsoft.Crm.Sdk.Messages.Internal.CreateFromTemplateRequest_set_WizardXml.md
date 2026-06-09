# Microsoft.Crm.Sdk.Messages.Internal.CreateFromTemplateRequest::set_WizardXml

- ea: `0x8a80`
- end: `0x8a92`
- name: `Microsoft.Crm.Sdk.Messages.Internal.CreateFromTemplateRequest::set_WizardXml`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8af0`

## string_xrefs

- `0x8a86`: `WizardXml`

## pseudocode

```c

```

## disassembly

```asm
0x8a80  ldarg.0
0x8a81  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8a86  ldstr    aWizardxml// "WizardXml"
0x8a8b  ldarg.1
0x8a8c  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8a91  ret
```
