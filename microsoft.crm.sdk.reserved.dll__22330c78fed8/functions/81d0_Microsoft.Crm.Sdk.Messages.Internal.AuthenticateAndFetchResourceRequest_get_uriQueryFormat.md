# Microsoft.Crm.Sdk.Messages.Internal.AuthenticateAndFetchResourceRequest::get_uriQueryFormat

- ea: `0x81d0`
- end: `0x81fa`
- name: `Microsoft.Crm.Sdk.Messages.Internal.AuthenticateAndFetchResourceRequest::get_uriQueryFormat`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x81d0`

## string_xrefs

- `0x81d6`: `uriQueryFormat`
- `0x81e8`: `uriQueryFormat`

## pseudocode

```c

```

## disassembly

```asm
0x81d0  ldarg.0
0x81d1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x81d6  ldstr    aUriqueryformat// "uriQueryFormat"
0x81db  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x81e0  brfalse.s loc_81F8
0x81e2  ldarg.0
0x81e3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x81e8  ldstr    aUriqueryformat// "uriQueryFormat"
0x81ed  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x81f2  castclass [mscorlib]System.String
0x81f7  ret
0x81f8  ldnull
0x81f9  ret
```
