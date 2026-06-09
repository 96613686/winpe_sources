# Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetSizeRequest::.ctor

- ea: `0x11240`
- end: `0x11267`
- name: `Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetSizeRequest::.ctor`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x11180`
- `0x111d0`
- `0x11220`

## string_xrefs

- `0x11247`: `DebugCacheGetSize`

## pseudocode

```c

```

## disassembly

```asm
0x11240  ldarg.0
0x11241  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x11246  ldarg.0
0x11247  ldstr    aDebugcachegets// "DebugCacheGetSize"
0x1124c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x11251  ldarg.0
0x11252  ldnull
0x11253  call     instance void Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetSizeRequest::set_CacheName(string value)
0x11258  ldarg.0
0x11259  ldnull
0x1125a  call     instance void Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetSizeRequest::set_OutputFormat(string value)
0x1125f  ldarg.0
0x11260  ldc.i4.0
0x11261  call     instance void Microsoft.Crm.Sdk.Messages.Internal.DebugCacheGetSizeRequest::set_IncludeLogs(bool value)
0x11266  ret
```
