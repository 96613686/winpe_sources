# Microsoft.Crm.Sdk.Messages.Internal.UpdateDocumentManagementSettingsRequest::get_EntityDocMgmtXml

- ea: `0xa840`
- end: `0xa86a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateDocumentManagementSettingsRequest::get_EntityDocMgmtXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xa840`

## string_xrefs

- `0xa846`: `EntityDocMgmtXml`
- `0xa858`: `EntityDocMgmtXml`

## pseudocode

```c

```

## disassembly

```asm
0xa840  ldarg.0
0xa841  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xa846  ldstr    aEntitydocmgmtx// "EntityDocMgmtXml"
0xa84b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xa850  brfalse.s loc_A868
0xa852  ldarg.0
0xa853  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xa858  ldstr    aEntitydocmgmtx// "EntityDocMgmtXml"
0xa85d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xa862  castclass [mscorlib]System.String
0xa867  ret
0xa868  ldnull
0xa869  ret
```
