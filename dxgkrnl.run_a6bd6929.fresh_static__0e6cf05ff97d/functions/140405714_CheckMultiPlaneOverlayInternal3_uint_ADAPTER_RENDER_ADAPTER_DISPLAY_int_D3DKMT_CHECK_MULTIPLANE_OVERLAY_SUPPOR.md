# CheckMultiPlaneOverlayInternal3(uint,ADAPTER_RENDER *,ADAPTER_DISPLAY *,int *,D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO *)

- ea: `0x140405714`
- end: `0x140405edf`
- name: `?CheckMultiPlaneOverlayInternal3@@YAJIPEAVADAPTER_RENDER@@PEAVADAPTER_DISPLAY@@PEAHPEAUD3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO@@@Z`
- size: `1995`
- prototype: `int(unsigned int, struct ADAPTER_RENDER *, struct ADAPTER_DISPLAY *, int *, struct D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO *)`
- caller_count: `2`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x140247a0c`
- `0x140397a34`

## callees

- `0x14001b9c0`
- `0x140041194`
- `0x1400559cc`
- `0x14006a1f4`
- `0x1400a0970`
- `0x1400a0bd0`
- `0x1401f31b0`
- `0x140219e40`
- `0x14021a0ec`
- `0x14021a384`
- `0x140392428`
- `0x140393c6c`
- `0x1403978bc`
- `0x140397938`
- `0x1403979b8`
- `0x1403a6174`
- `0x1403a9230`
- `0x1403b1418`
- `0x140405714`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14040585b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14040588b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1404059d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405a06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405a2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405a5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405a89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405ab1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405da8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405dd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405e02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405e29`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405e56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405e85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405ead`
- `ntoskrnl!ExFreePoolWithTag` at `0x14040585b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14040588b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1404059d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405a06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405a2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405a5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405a89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405ab1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405da8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405dd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405e02`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405e29`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405e56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405e85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140405ead`
- `ntoskrnl!PsGetCurrentProcess` at `0x140405791`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040580e`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404058c0`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040591d`
- `ntoskrnl!PsGetCurrentProcess` at `0x140405989`
- `ntoskrnl!PsGetCurrentProcess` at `0x140405791`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040580e`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404058c0`
- `ntoskrnl!PsGetCurrentProcess` at `0x14040591d`
- `ntoskrnl!PsGetCurrentProcess` at `0x140405989`
- `watchdog!WdLogSingleEntry3` at `0x1404057ae`
- `watchdog!WdLogSingleEntry3` at `0x14040582b`
- `watchdog!WdLogSingleEntry3` at `0x1404058dd`
- `watchdog!WdLogSingleEntry3` at `0x14040593a`
- `watchdog!WdLogSingleEntry3` at `0x1404059a7`
- `watchdog!WdLogSingleEntry3` at `0x1404057ae`
- `watchdog!WdLogSingleEntry3` at `0x14040582b`
- `watchdog!WdLogSingleEntry3` at `0x1404058dd`
- `watchdog!WdLogSingleEntry3` at `0x14040593a`
- `watchdog!WdLogSingleEntry3` at `0x1404059a7`
- `watchdog!WdLogSingleEntry0` at `0x140405ba9`
- `watchdog!WdLogSingleEntry0` at `0x140405c04`
- `watchdog!WdLogSingleEntry0` at `0x140405ba9`
- `watchdog!WdLogSingleEntry0` at `0x140405c04`

## string_xrefs

- `0x140405c15`: `ActualPostCompositionCount <= NumVidPnSources`
- `0x140405cde`: `Invalid allocation in CheckMPO cache`

## pseudocode

```c

```
