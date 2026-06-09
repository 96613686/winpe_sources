# Microsoft.Crm.Sdk.Messages.Internal.GetImportMapXmlRequest::get_wizardDataXml

- ea: `0x13410`
- end: `0x1343a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetImportMapXmlRequest::get_wizardDataXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x13410`

## string_xrefs

- `0x13416`: `wizardDataXml`
- `0x13428`: `wizardDataXml`

## pseudocode

```c

```

## disassembly

```asm
0x13410  ldarg.0
0x13411  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x13416  ldstr    aWizarddataxml// "wizardDataXml"
0x1341b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x13420  brfalse.s loc_13438
0x13422  ldarg.0
0x13423  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x13428  ldstr    aWizarddataxml// "wizardDataXml"
0x1342d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x13432  castclass [mscorlib]System.String
0x13437  ret
0x13438  ldnull
0x13439  ret
```
