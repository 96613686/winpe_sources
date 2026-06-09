# Microsoft.Crm.Sdk.Messages.Internal.GetWopiExcelClientInfoResponse::get_AccessToken

- ea: `0x14300`
- end: `0x1432a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetWopiExcelClientInfoResponse::get_AccessToken`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14300`

## string_xrefs

- `0x14306`: `AccessToken`
- `0x14318`: `AccessToken`

## pseudocode

```c

```

## disassembly

```asm
0x14300  ldarg.0
0x14301  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x14306  ldstr    aAccesstoken// "AccessToken"
0x1430b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x14310  brfalse.s loc_14328
0x14312  ldarg.0
0x14313  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x14318  ldstr    aAccesstoken// "AccessToken"
0x1431d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x14322  castclass [mscorlib]System.String
0x14327  ret
0x14328  ldnull
0x14329  ret
```
