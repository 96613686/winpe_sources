# Microsoft.Crm.Sdk.Messages.Internal.GetWopiExcelClientInfoResponse::get_ExcelOnlineUri

- ea: `0x142d0`
- end: `0x142fa`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetWopiExcelClientInfoResponse::get_ExcelOnlineUri`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x142d0`

## string_xrefs

- `0x142d6`: `ExcelOnlineUri`
- `0x142e8`: `ExcelOnlineUri`

## pseudocode

```c

```

## disassembly

```asm
0x142d0  ldarg.0
0x142d1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x142d6  ldstr    aExcelonlineuri// "ExcelOnlineUri"
0x142db  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x142e0  brfalse.s loc_142F8
0x142e2  ldarg.0
0x142e3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x142e8  ldstr    aExcelonlineuri// "ExcelOnlineUri"
0x142ed  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x142f2  castclass [mscorlib]System.String
0x142f7  ret
0x142f8  ldnull
0x142f9  ret
```
