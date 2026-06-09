# Microsoft.Crm.Common.Application.Pages.Common.WindowInformation::.ctor

- ea: `0x1d480`
- end: `0x1d49d`
- name: `Microsoft.Crm.Common.Application.Pages.Common.WindowInformation::.ctor`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x1d481`: `CRMWindowInfo_CacheKey`
- `0x1d48c`: `_CRMWindowInfoFcb_CacheKey`

## pseudocode

```c

```

## disassembly

```asm
0x1d480  ldarg.0
0x1d481  ldstr    aCrmwindowinfoC// "CRMWindowInfo_CacheKey"
0x1d486  stfld    string Microsoft.Crm.Common.Application.Pages.Common.WindowInformation::_functionCacheKey
0x1d48b  ldarg.0
0x1d48c  ldstr    aCrmwindowinfof// "_CRMWindowInfoFcb_CacheKey"
0x1d491  stfld    string Microsoft.Crm.Common.Application.Pages.Common.WindowInformation::_functionCacheKeyFcb
0x1d496  ldarg.0
0x1d497  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::.ctor()
0x1d49c  ret
```
