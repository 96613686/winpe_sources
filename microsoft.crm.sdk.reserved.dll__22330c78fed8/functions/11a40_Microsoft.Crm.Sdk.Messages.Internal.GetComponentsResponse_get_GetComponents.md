# Microsoft.Crm.Sdk.Messages.Internal.GetComponentsResponse::get_GetComponents

- ea: `0x11a40`
- end: `0x11a6a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetComponentsResponse::get_GetComponents`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x11a40`

## string_xrefs

- `0x11a46`: `GetComponents`
- `0x11a58`: `GetComponents`

## pseudocode

```c

```

## disassembly

```asm
0x11a40  ldarg.0
0x11a41  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11a46  ldstr    aGetcomponents// "GetComponents"
0x11a4b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11a50  brfalse.s loc_11A68
0x11a52  ldarg.0
0x11a53  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11a58  ldstr    aGetcomponents// "GetComponents"
0x11a5d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11a62  castclass [mscorlib]System.String
0x11a67  ret
0x11a68  ldnull
0x11a69  ret
```
