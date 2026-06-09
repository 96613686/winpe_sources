# Microsoft.Crm.Sdk.Messages.Internal.UpdateUpsertAttributesResponse::get_updateResult

- ea: `0x13700`
- end: `0x1372a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateUpsertAttributesResponse::get_updateResult`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x13700`

## string_xrefs

- `0x13706`: `updateResult`
- `0x13718`: `updateResult`

## pseudocode

```c

```

## disassembly

```asm
0x13700  ldarg.0
0x13701  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x13706  ldstr    aUpdateresult// "updateResult"
0x1370b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x13710  brfalse.s loc_13728
0x13712  ldarg.0
0x13713  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x13718  ldstr    aUpdateresult// "updateResult"
0x1371d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x13722  unbox.any [mscorlib]System.Boolean
0x13727  ret
0x13728  ldc.i4.0
0x13729  ret
```
