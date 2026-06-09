# Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetSizeResponse::get_CacheSizeDetails

- ea: `0x11290`
- end: `0x112ba`
- name: `Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetSizeResponse::get_CacheSizeDetails`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x11290`

## string_xrefs

- `0x11296`: `CacheSizeDetails`
- `0x112a8`: `CacheSizeDetails`

## pseudocode

```c

```

## disassembly

```asm
0x11290  ldarg.0
0x11291  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11296  ldstr    aCachesizedetai// "CacheSizeDetails"
0x1129b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x112a0  brfalse.s loc_112B8
0x112a2  ldarg.0
0x112a3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x112a8  ldstr    aCachesizedetai// "CacheSizeDetails"
0x112ad  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x112b2  castclass [mscorlib]System.String
0x112b7  ret
0x112b8  ldnull
0x112b9  ret
```
