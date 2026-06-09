# Microsoft.Crm.Sdk.Messages.Internal.RetrieveDocumentsFromAllLocationsAndSharedRequest::get_PageToken

- ea: `0xc1d0`
- end: `0xc1fa`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveDocumentsFromAllLocationsAndSharedRequest::get_PageToken`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xc1d0`

## string_xrefs

- `0xc1d6`: `PageToken`
- `0xc1e8`: `PageToken`

## pseudocode

```c

```

## disassembly

```asm
0xc1d0  ldarg.0
0xc1d1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xc1d6  ldstr    aPagetoken// "PageToken"
0xc1db  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0xc1e0  brfalse.s loc_C1F8
0xc1e2  ldarg.0
0xc1e3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0xc1e8  ldstr    aPagetoken// "PageToken"
0xc1ed  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xc1f2  castclass [mscorlib]System.String
0xc1f7  ret
0xc1f8  ldnull
0xc1f9  ret
```
