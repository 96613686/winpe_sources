# Microsoft.Crm.Sdk.Messages.Internal.UpdateDelimitersRequest::get_wizardDataXml

- ea: `0x134e0`
- end: `0x1350a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateDelimitersRequest::get_wizardDataXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x134e0`

## string_xrefs

- `0x134e6`: `wizardDataXml`
- `0x134f8`: `wizardDataXml`

## pseudocode

```c

```

## disassembly

```asm
0x134e0  ldarg.0
0x134e1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x134e6  ldstr    aWizarddataxml// "wizardDataXml"
0x134eb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x134f0  brfalse.s loc_13508
0x134f2  ldarg.0
0x134f3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x134f8  ldstr    aWizarddataxml// "wizardDataXml"
0x134fd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x13502  castclass [mscorlib]System.String
0x13507  ret
0x13508  ldnull
0x13509  ret
```
