# Microsoft.Crm.Sdk.Messages.Internal.RetrieveAADAccessTokenResponse::get_AccessToken

- ea: `0x10530`
- end: `0x1055a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveAADAccessTokenResponse::get_AccessToken`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10530`

## string_xrefs

- `0x10536`: `AccessToken`
- `0x10548`: `AccessToken`

## pseudocode

```c

```

## disassembly

```asm
0x10530  ldarg.0
0x10531  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x10536  ldstr    aAccesstoken// "AccessToken"
0x1053b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10540  brfalse.s loc_10558
0x10542  ldarg.0
0x10543  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x10548  ldstr    aAccesstoken// "AccessToken"
0x1054d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10552  castclass [mscorlib]System.String
0x10557  ret
0x10558  ldnull
0x10559  ret
```
