# Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::get_DeleteImportHistory

- ea: `0x125f0`
- end: `0x1261a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.BulkDeleteImportedRecordsRequest::get_DeleteImportHistory`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x125f0`

## string_xrefs

- `0x125f6`: `DeleteImportHistory`
- `0x12608`: `DeleteImportHistory`

## pseudocode

```c

```

## disassembly

```asm
0x125f0  ldarg.0
0x125f1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x125f6  ldstr    aDeleteimporthi// "DeleteImportHistory"
0x125fb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12600  brfalse.s loc_12618
0x12602  ldarg.0
0x12603  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x12608  ldstr    aDeleteimporthi// "DeleteImportHistory"
0x1260d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x12612  unbox.any [mscorlib]System.Boolean
0x12617  ret
0x12618  ldc.i4.0
0x12619  ret
```
