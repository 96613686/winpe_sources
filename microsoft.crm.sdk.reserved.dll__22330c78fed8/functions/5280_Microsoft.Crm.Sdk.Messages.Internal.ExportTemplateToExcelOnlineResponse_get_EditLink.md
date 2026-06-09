# Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineResponse::get_EditLink

- ea: `0x5280`
- end: `0x52aa`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportTemplateToExcelOnlineResponse::get_EditLink`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5280`

## string_xrefs

- `0x5286`: `EditLink`
- `0x5298`: `EditLink`

## pseudocode

```c

```

## disassembly

```asm
0x5280  ldarg.0
0x5281  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x5286  ldstr    aEditlink// "EditLink"
0x528b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x5290  brfalse.s loc_52A8
0x5292  ldarg.0
0x5293  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x5298  ldstr    aEditlink// "EditLink"
0x529d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x52a2  castclass [mscorlib]System.String
0x52a7  ret
0x52a8  ldnull
0x52a9  ret
```
