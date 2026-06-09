# Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelRequest::get_FetchXml

- ea: `0x10a70`
- end: `0x10a9a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10a70`

## string_xrefs

- `0x10a76`: `FetchXml`
- `0x10a88`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x10a70  ldarg.0
0x10a71  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10a76  ldstr    aFetchxml// "FetchXml"
0x10a7b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10a80  brfalse.s loc_10A98
0x10a82  ldarg.0
0x10a83  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10a88  ldstr    aFetchxml// "FetchXml"
0x10a8d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10a92  castclass [mscorlib]System.String
0x10a97  ret
0x10a98  ldnull
0x10a99  ret
```
