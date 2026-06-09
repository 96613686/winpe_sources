# Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelOnlineResponse::get_EditLink

- ea: `0x12460`
- end: `0x1248a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.ExportToExcelOnlineResponse::get_EditLink`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x12460`

## string_xrefs

- `0x12466`: `EditLink`
- `0x12478`: `EditLink`

## pseudocode

```c

```

## disassembly

```asm
0x12460  ldarg.0
0x12461  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x12466  ldstr    aEditlink// "EditLink"
0x1246b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12470  brfalse.s loc_12488
0x12472  ldarg.0
0x12473  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x12478  ldstr    aEditlink// "EditLink"
0x1247d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x12482  castclass [mscorlib]System.String
0x12487  ret
0x12488  ldnull
0x12489  ret
```
