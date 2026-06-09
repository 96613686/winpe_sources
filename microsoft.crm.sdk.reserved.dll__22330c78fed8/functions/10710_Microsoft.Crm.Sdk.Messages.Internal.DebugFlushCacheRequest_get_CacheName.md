# Microsoft.Crm.Sdk.Messages.Internal.DebugFlushCacheRequest::get_CacheName

- ea: `0x10710`
- end: `0x1073a`
- name: `Microsoft.Crm.Sdk.Messages.Internal.DebugFlushCacheRequest::get_CacheName`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10710`

## string_xrefs

- `0x10716`: `CacheName`
- `0x10728`: `CacheName`

## pseudocode

```c

```

## disassembly

```asm
0x10710  ldarg.0
0x10711  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10716  ldstr    aCachename// "CacheName"
0x1071b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x10720  brfalse.s loc_10738
0x10722  ldarg.0
0x10723  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x10728  ldstr    aCachename// "CacheName"
0x1072d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x10732  castclass [mscorlib]System.String
0x10737  ret
0x10738  ldnull
0x10739  ret
```
