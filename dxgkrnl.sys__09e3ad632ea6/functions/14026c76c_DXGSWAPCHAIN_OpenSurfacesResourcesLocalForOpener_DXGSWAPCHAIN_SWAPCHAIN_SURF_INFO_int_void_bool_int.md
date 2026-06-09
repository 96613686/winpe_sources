# DXGSWAPCHAIN::OpenSurfacesResourcesLocalForOpener(DXGSWAPCHAIN::SWAPCHAIN_SURF_INFO *,int,void * *,bool,int)

- ea: `0x14026c76c`
- end: `0x14026cd8d`
- name: `?OpenSurfacesResourcesLocalForOpener@DXGSWAPCHAIN@@AEAAJPEAUSWAPCHAIN_SURF_INFO@1@HPEAPEAX_NH@Z`
- size: `1569`
- prototype: `__int64 __usercall@<rax>(DXGSWAPCHAIN *__hidden this@<rcx>, struct DXGSWAPCHAIN::SWAPCHAIN_SURF_INFO *@<rdx>, int@<r8d>, void **@<r9>, bool, int)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x14026c5c4`
- `0x1403a2b74`

## callees

- `0x140012540`
- `0x14001b9c0`
- `0x14001bea0`
- `0x140030a30`
- `0x140033da4`
- `0x140047d74`
- `0x140048a5c`
- `0x140054160`
- `0x1400a1000`
- `0x14026bf34`
- `0x14026c76c`
- `0x14032a5c4`
- `0x1403ba56c`
- `0x1403ca050`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14026cd4d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14026cd4d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14026cd41`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14026cd41`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026c84f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026c89b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026c8d5`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026c956`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026cac6`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026cbd3`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026cc00`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026c84f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026c89b`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026c8d5`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026c956`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026cac6`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026cbd3`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026cc00`
- `ntoskrnl!ObDuplicateObject` at `0x14026c882`
- `ntoskrnl!ObDuplicateObject` at `0x14026c987`
- `ntoskrnl!ObDuplicateObject` at `0x14026c882`
- `ntoskrnl!ObDuplicateObject` at `0x14026c987`
- `watchdog!WdLogSingleEntry4` at `0x14026c8bf`
- `watchdog!WdLogSingleEntry4` at `0x14026c8bf`
- `watchdog!WdLogSingleEntry2` at `0x14026c9a7`
- `watchdog!WdLogSingleEntry2` at `0x14026ca58`
- `watchdog!WdLogSingleEntry2` at `0x14026cadd`
- `watchdog!WdLogSingleEntry2` at `0x14026cbea`
- `watchdog!WdLogSingleEntry2` at `0x14026c9a7`
- `watchdog!WdLogSingleEntry2` at `0x14026ca58`
- `watchdog!WdLogSingleEntry2` at `0x14026cadd`
- `watchdog!WdLogSingleEntry2` at `0x14026cbea`
- `watchdog!WdLogSingleEntry0` at `0x14026c7ad`
- `watchdog!WdLogSingleEntry0` at `0x14026cb7e`
- `watchdog!WdLogSingleEntry0` at `0x14026ccdf`
- `watchdog!WdLogSingleEntry0` at `0x14026c7ad`
- `watchdog!WdLogSingleEntry0` at `0x14026cb7e`
- `watchdog!WdLogSingleEntry0` at `0x14026ccdf`

## string_xrefs

- `0x14026cc0f`: `Failed to open GPU fence 0x%I64x in process 0x%I64x`
- `0x14026ca6e`: `Failed to open Fence Nt handle 0x%I64x, error 0x%I64x`

## pseudocode

```c

```
