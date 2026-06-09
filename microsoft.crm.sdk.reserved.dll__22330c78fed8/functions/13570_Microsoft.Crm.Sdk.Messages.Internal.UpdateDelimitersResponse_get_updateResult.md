# Microsoft.Crm.Sdk.Messages.Internal.UpdateDelimitersResponse::get_updateResult

- ea: `0x13570`
- end: `0x1359a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateDelimitersResponse::get_updateResult`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x13570`

## string_xrefs

- `0x13576`: `updateResult`
- `0x13588`: `updateResult`

## pseudocode

```c

```

## disassembly

```asm
0x13570  ldarg.0
0x13571  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x13576  ldstr    aUpdateresult// "updateResult"
0x1357b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x13580  brfalse.s loc_13598
0x13582  ldarg.0
0x13583  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x13588  ldstr    aUpdateresult// "updateResult"
0x1358d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x13592  unbox.any [mscorlib]System.Boolean
0x13597  ret
0x13598  ldc.i4.0
0x13599  ret
```
