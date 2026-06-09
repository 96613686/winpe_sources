# Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetContentsResponse::get_CacheItems

- ea: `0x11110`
- end: `0x1113a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetContentsResponse::get_CacheItems`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x11110`

## string_xrefs

- `0x11116`: `CacheItems`
- `0x11128`: `CacheItems`

## pseudocode

```c

```

## disassembly

```asm
0x11110  ldarg.0
0x11111  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11116  ldstr    aCacheitems// "CacheItems"
0x1111b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11120  brfalse.s loc_11138
0x11122  ldarg.0
0x11123  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x11128  ldstr    aCacheitems// "CacheItems"
0x1112d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11132  castclass class Microsoft.Crm.Sdk.Messages.CacheItem[]
0x11137  ret
0x11138  ldnull
0x11139  ret
```
