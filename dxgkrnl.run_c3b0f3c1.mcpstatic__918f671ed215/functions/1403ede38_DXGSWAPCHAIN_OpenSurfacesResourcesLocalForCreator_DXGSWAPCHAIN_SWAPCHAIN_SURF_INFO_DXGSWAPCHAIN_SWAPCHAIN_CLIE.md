# DXGSWAPCHAIN::OpenSurfacesResourcesLocalForCreator(DXGSWAPCHAIN::SWAPCHAIN_SURF_INFO *,DXGSWAPCHAIN::SWAPCHAIN_CLIENT_SURF_INFO *,void *,int,bool)

- ea: `0x1403ede38`
- end: `0x1403ee49e`
- name: `?OpenSurfacesResourcesLocalForCreator@DXGSWAPCHAIN@@AEAAJPEAUSWAPCHAIN_SURF_INFO@1@PEAUSWAPCHAIN_CLIENT_SURF_INFO@1@PEAXH_N@Z`
- size: `1638`
- prototype: `__int64 __fastcall(struct _KTHREAD **this, struct DXGSWAPCHAIN::SWAPCHAIN_SURF_INFO *, struct DXGSWAPCHAIN::SWAPCHAIN_CLIENT_SURF_INFO *, void *, int, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1401bb1a4`

## callees

- `0x140012540`
- `0x14001b9c0`
- `0x14001bea0`
- `0x140030a30`
- `0x140033da4`
- `0x140047d74`
- `0x140048a5c`
- `0x14007c0ec`
- `0x1400a1000`
- `0x14032a5c4`
- `0x1403ba56c`
- `0x1403ca050`
- `0x1403ede38`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403ee462`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403ee462`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403ee456`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403ee456`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edfc0`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edfcf`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ee078`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ee08b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ee1fa`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ee228`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ee34d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edfc0`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edfcf`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ee078`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ee08b`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ee1fa`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ee228`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ee34d`
- `ntoskrnl!ObfDereferenceObject` at `0x1403edfb0`
- `ntoskrnl!ObfDereferenceObject` at `0x1403edfb0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1403edee8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1403edee8`
- `ntoskrnl!ObDuplicateObject` at `0x1403edfff`
- `ntoskrnl!ObDuplicateObject` at `0x1403ee0c4`
- `ntoskrnl!ObDuplicateObject` at `0x1403edfff`
- `ntoskrnl!ObDuplicateObject` at `0x1403ee0c4`
- `watchdog!WdLogSingleEntry2` at `0x1403edf06`
- `watchdog!WdLogSingleEntry2` at `0x1403ee01d`
- `watchdog!WdLogSingleEntry2` at `0x1403ee0e2`
- `watchdog!WdLogSingleEntry2` at `0x1403ee172`
- `watchdog!WdLogSingleEntry2` at `0x1403ee212`
- `watchdog!WdLogSingleEntry2` at `0x1403ee365`
- `watchdog!WdLogSingleEntry2` at `0x1403edf06`
- `watchdog!WdLogSingleEntry2` at `0x1403ee01d`
- `watchdog!WdLogSingleEntry2` at `0x1403ee0e2`
- `watchdog!WdLogSingleEntry2` at `0x1403ee172`
- `watchdog!WdLogSingleEntry2` at `0x1403ee212`
- `watchdog!WdLogSingleEntry2` at `0x1403ee365`
- `watchdog!WdLogSingleEntry0` at `0x1403ede7a`
- `watchdog!WdLogSingleEntry0` at `0x1403ee2fb`
- `watchdog!WdLogSingleEntry0` at `0x1403ee3f9`
- `watchdog!WdLogSingleEntry0` at `0x1403ede7a`
- `watchdog!WdLogSingleEntry0` at `0x1403ee2fb`
- `watchdog!WdLogSingleEntry0` at `0x1403ee3f9`

## string_xrefs

- `0x1403ee238`: `Failed to open GPU fence 0x%I64x in process 0x%I64x`
- `0x1403ee183`: `Failed to open Fence Nt handle 0x%I64x, error 0x%I64x`

## pseudocode

```c

```
