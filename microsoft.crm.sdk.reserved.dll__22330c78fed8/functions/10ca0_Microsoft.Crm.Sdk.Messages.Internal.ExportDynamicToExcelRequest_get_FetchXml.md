# Microsoft.Crm.Sdk.Messages.Internal.ExportDynamicToExcelRequest::get_FetchXml

- ea: `0x10ca0`
- end: `0x10cca`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportDynamicToExcelRequest::get_FetchXml`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10ca0`

## string_xrefs

- `0x10ca6`: `FetchXml`
- `0x10cb8`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x10ca0  ldarg.0
0x10ca1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10ca6  ldstr    aFetchxml// "FetchXml"
0x10cab  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10cb0  brfalse.s loc_10CC8
0x10cb2  ldarg.0
0x10cb3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10cb8  ldstr    aFetchxml// "FetchXml"
0x10cbd  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10cc2  castclass [mscorlib]System.String
0x10cc7  ret
0x10cc8  ldnull
0x10cc9  ret
```
