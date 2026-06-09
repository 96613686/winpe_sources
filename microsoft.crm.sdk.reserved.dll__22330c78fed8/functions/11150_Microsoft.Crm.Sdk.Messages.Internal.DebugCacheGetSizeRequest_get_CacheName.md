# Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetSizeRequest::get_CacheName

- ea: `0x11150`
- end: `0x1117a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetSizeRequest::get_CacheName`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x11150`

## string_xrefs

- `0x11156`: `CacheName`
- `0x11168`: `CacheName`

## pseudocode

```c

```

## disassembly

```asm
0x11150  ldarg.0
0x11151  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x11156  ldstr    aCachename// "CacheName"
0x1115b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11160  brfalse.s loc_11178
0x11162  ldarg.0
0x11163  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x11168  ldstr    aCachename// "CacheName"
0x1116d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x11172  castclass [mscorlib]System.String
0x11177  ret
0x11178  ldnull
0x11179  ret
```
