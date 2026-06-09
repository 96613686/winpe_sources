# Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::get_FetchXml

- ea: `0x10940`
- end: `0x1096a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10940`

## string_xrefs

- `0x10946`: `FetchXml`
- `0x10958`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x10940  ldarg.0
0x10941  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10946  ldstr    aFetchxml// "FetchXml"
0x1094b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10950  brfalse.s loc_10968
0x10952  ldarg.0
0x10953  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10958  ldstr    aFetchxml// "FetchXml"
0x1095d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10962  castclass [mscorlib]System.String
0x10967  ret
0x10968  ldnull
0x10969  ret
```
