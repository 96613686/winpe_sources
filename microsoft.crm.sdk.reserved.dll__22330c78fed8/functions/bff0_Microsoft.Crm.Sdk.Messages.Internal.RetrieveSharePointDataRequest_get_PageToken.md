# Microsoft.Crm.Sdk.Messages.Internal.RetrieveSharePointDataRequest::get_PageToken

- ea: `0xbff0`
- end: `0xc01a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveSharePointDataRequest::get_PageToken`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xbff0`

## string_xrefs

- `0xbff6`: `PageToken`
- `0xc008`: `PageToken`

## pseudocode

```c

```

## disassembly

```asm
0xbff0  ldarg.0
0xbff1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xbff6  ldstr    aPagetoken// "PageToken"
0xbffb  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xc000  brfalse.s loc_C018
0xc002  ldarg.0
0xc003  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xc008  ldstr    aPagetoken// "PageToken"
0xc00d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xc012  castclass [mscorlib]System.String
0xc017  ret
0xc018  ldnull
0xc019  ret
```
