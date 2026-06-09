# Microsoft.Crm.Sdk.Messages.Internal.UpdateFromTemplateRequest::get_WizardXml

- ea: `0x8be0`
- end: `0x8c0a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateFromTemplateRequest::get_WizardXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x8be0`

## string_xrefs

- `0x8be6`: `WizardXml`
- `0x8bf8`: `WizardXml`

## pseudocode

```c

```

## disassembly

```asm
0x8be0  ldarg.0
0x8be1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8be6  ldstr    aWizardxml// "WizardXml"
0x8beb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x8bf0  brfalse.s loc_8C08
0x8bf2  ldarg.0
0x8bf3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x8bf8  ldstr    aWizardxml// "WizardXml"
0x8bfd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x8c02  castclass [mscorlib]System.String
0x8c07  ret
0x8c08  ldnull
0x8c09  ret
```
