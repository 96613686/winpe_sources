# DXGSWAPCHAIN::OpenSurfacesResourcesLocalForCreator(DXGSWAPCHAIN::SWAPCHAIN_SURF_INFO *,DXGSWAPCHAIN::SWAPCHAIN_CLIENT_SURF_INFO *,void *,int,bool)

- ea: `0x1403ed978`
- end: `0x1403edfde`
- name: `?OpenSurfacesResourcesLocalForCreator@DXGSWAPCHAIN@@AEAAJPEAUSWAPCHAIN_SURF_INFO@1@PEAUSWAPCHAIN_CLIENT_SURF_INFO@1@PEAXH_N@Z`
- size: `1638`
- prototype: `int(DXGSWAPCHAIN *__hidden this, struct DXGSWAPCHAIN::SWAPCHAIN_SURF_INFO *, struct DXGSWAPCHAIN::SWAPCHAIN_CLIENT_SURF_INFO *, void *, int, bool)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1401b85a4`

## callees

- `0x140012380`
- `0x14001b890`
- `0x14001bd70`
- `0x140030860`
- `0x140033bd4`
- `0x140047b74`
- `0x14004885c`
- `0x14007b854`
- `0x1400a0540`
- `0x140323854`
- `0x14032f6b0`
- `0x1403bb24c`
- `0x1403ed978`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403edfa2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403edfa2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403edf96`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1403edf96`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edb00`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edb0f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edbb8`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edbcb`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edd3a`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edd68`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ede8d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edb00`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edb0f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edbb8`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edbcb`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edd3a`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403edd68`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ede8d`
- `ntoskrnl!ObfDereferenceObject` at `0x1403edaf0`
- `ntoskrnl!ObfDereferenceObject` at `0x1403edaf0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1403eda28`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1403eda28`
- `ntoskrnl!ObDuplicateObject` at `0x1403edb3f`
- `ntoskrnl!ObDuplicateObject` at `0x1403edc04`
- `ntoskrnl!ObDuplicateObject` at `0x1403edb3f`
- `ntoskrnl!ObDuplicateObject` at `0x1403edc04`
- `watchdog!WdLogSingleEntry2` at `0x1403eda46`
- `watchdog!WdLogSingleEntry2` at `0x1403edb5d`
- `watchdog!WdLogSingleEntry2` at `0x1403edc22`
- `watchdog!WdLogSingleEntry2` at `0x1403edcb2`
- `watchdog!WdLogSingleEntry2` at `0x1403edd52`
- `watchdog!WdLogSingleEntry2` at `0x1403edea5`
- `watchdog!WdLogSingleEntry2` at `0x1403eda46`
- `watchdog!WdLogSingleEntry2` at `0x1403edb5d`
- `watchdog!WdLogSingleEntry2` at `0x1403edc22`
- `watchdog!WdLogSingleEntry2` at `0x1403edcb2`
- `watchdog!WdLogSingleEntry2` at `0x1403edd52`
- `watchdog!WdLogSingleEntry2` at `0x1403edea5`
- `watchdog!WdLogSingleEntry0` at `0x1403ed9ba`
- `watchdog!WdLogSingleEntry0` at `0x1403ede3b`
- `watchdog!WdLogSingleEntry0` at `0x1403edf39`
- `watchdog!WdLogSingleEntry0` at `0x1403ed9ba`
- `watchdog!WdLogSingleEntry0` at `0x1403ede3b`
- `watchdog!WdLogSingleEntry0` at `0x1403edf39`

## string_xrefs

- `0x1403edd78`: `Failed to open GPU fence 0x%I64x in process 0x%I64x`
- `0x1403edcc3`: `Failed to open Fence Nt handle 0x%I64x, error 0x%I64x`

## pseudocode

```c

```
