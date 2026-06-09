# Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetContentsRequest::get_CacheName

- ea: `0x11080`
- end: `0x110aa`
- name: `Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetContentsRequest::get_CacheName`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x11080`

## string_xrefs

- `0x11086`: `CacheName`
- `0x11098`: `CacheName`

## pseudocode

```c

```

## disassembly

```asm
0x11080  ldarg.0
0x11081  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x11086  ldstr    aCachename// "CacheName"
0x1108b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x11090  brfalse.s loc_110A8
0x11092  ldarg.0
0x11093  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x11098  ldstr    aCachename// "CacheName"
0x1109d  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x110a2  castclass [mscorlib]System.String
0x110a7  ret
0x110a8  ldnull
0x110a9  ret
```
