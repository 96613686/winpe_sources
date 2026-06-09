# DXGSWAPCHAIN::OpenSurfacesResourcesLocalForOpener(DXGSWAPCHAIN::SWAPCHAIN_SURF_INFO *,int,void * *,bool,int)

- ea: `0x1402671ac`
- end: `0x1402677cd`
- name: `?OpenSurfacesResourcesLocalForOpener@DXGSWAPCHAIN@@AEAAJPEAUSWAPCHAIN_SURF_INFO@1@HPEAPEAX_NH@Z`
- size: `1569`
- prototype: `__int64 __usercall@<rax>(DXGSWAPCHAIN *__hidden this@<rcx>, struct DXGSWAPCHAIN::SWAPCHAIN_SURF_INFO *@<rdx>, int@<r8d>, void **@<r9>, bool, int)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x140267004`
- `0x1403a1d94`

## callees

- `0x140012380`
- `0x14001b890`
- `0x14001bd70`
- `0x140030860`
- `0x140033bd4`
- `0x140047b74`
- `0x14004885c`
- `0x140053f80`
- `0x1400a0540`
- `0x140266974`
- `0x1402671ac`
- `0x140323854`
- `0x14032f6b0`
- `0x1403bb24c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14026778d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14026778d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140267781`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140267781`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026728f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402672db`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267315`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267396`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267506`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267613`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267640`
- `ntoskrnl!PsGetCurrentProcess` at `0x14026728f`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402672db`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267315`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267396`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267506`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267613`
- `ntoskrnl!PsGetCurrentProcess` at `0x140267640`
- `ntoskrnl!ObDuplicateObject` at `0x1402672c2`
- `ntoskrnl!ObDuplicateObject` at `0x1402673c7`
- `ntoskrnl!ObDuplicateObject` at `0x1402672c2`
- `ntoskrnl!ObDuplicateObject` at `0x1402673c7`
- `watchdog!WdLogSingleEntry4` at `0x1402672ff`
- `watchdog!WdLogSingleEntry4` at `0x1402672ff`
- `watchdog!WdLogSingleEntry2` at `0x1402673e7`
- `watchdog!WdLogSingleEntry2` at `0x140267498`
- `watchdog!WdLogSingleEntry2` at `0x14026751d`
- `watchdog!WdLogSingleEntry2` at `0x14026762a`
- `watchdog!WdLogSingleEntry2` at `0x1402673e7`
- `watchdog!WdLogSingleEntry2` at `0x140267498`
- `watchdog!WdLogSingleEntry2` at `0x14026751d`
- `watchdog!WdLogSingleEntry2` at `0x14026762a`
- `watchdog!WdLogSingleEntry0` at `0x1402671ed`
- `watchdog!WdLogSingleEntry0` at `0x1402675be`
- `watchdog!WdLogSingleEntry0` at `0x14026771f`
- `watchdog!WdLogSingleEntry0` at `0x1402671ed`
- `watchdog!WdLogSingleEntry0` at `0x1402675be`
- `watchdog!WdLogSingleEntry0` at `0x14026771f`

## string_xrefs

- `0x14026764f`: `Failed to open GPU fence 0x%I64x in process 0x%I64x`
- `0x1402674ae`: `Failed to open Fence Nt handle 0x%I64x, error 0x%I64x`

## pseudocode

```c

```
