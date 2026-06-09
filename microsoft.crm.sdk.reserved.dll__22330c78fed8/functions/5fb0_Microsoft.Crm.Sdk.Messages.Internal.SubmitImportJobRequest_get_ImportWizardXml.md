# Microsoft.Crm.Sdk.Messages.Internal.SubmitImportJobRequest::get_ImportWizardXml

- ea: `0x5fb0`
- end: `0x5fda`
- name: `Microsoft.Crm.Sdk.Messages.Internal.SubmitImportJobRequest::get_ImportWizardXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5fb0`

## string_xrefs

- `0x5fb6`: `ImportWizardXml`
- `0x5fc8`: `ImportWizardXml`

## pseudocode

```c

```

## disassembly

```asm
0x5fb0  ldarg.0
0x5fb1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5fb6  ldstr    aImportwizardxm// "ImportWizardXml"
0x5fbb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x5fc0  brfalse.s loc_5FD8
0x5fc2  ldarg.0
0x5fc3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x5fc8  ldstr    aImportwizardxm// "ImportWizardXml"
0x5fcd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x5fd2  castclass [mscorlib]System.String
0x5fd7  ret
0x5fd8  ldnull
0x5fd9  ret
```
