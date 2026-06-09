# CheckMultiPlaneOverlayInternal3(uint,ADAPTER_RENDER *,ADAPTER_DISPLAY *,int *,D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO *)

- ea: `0x1404063c4`
- end: `0x140406b8f`
- name: `?CheckMultiPlaneOverlayInternal3@@YAJIPEAVADAPTER_RENDER@@PEAVADAPTER_DISPLAY@@PEAHPEAUD3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO@@@Z`
- size: `1995`
- prototype: `int(unsigned int, struct ADAPTER_RENDER *, struct ADAPTER_DISPLAY *, int *, struct D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO *)`
- caller_count: `2`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x140244d64`
- `0x140396c24`

## callees

- `0x14001b890`
- `0x140040f34`
- `0x14005575c`
- `0x140069c94`
- `0x14009fea0`
- `0x1400a0100`
- `0x1401f0de0`
- `0x1402177f0`
- `0x140217a9c`
- `0x140217d34`
- `0x14034056c`
- `0x140393494`
- `0x140396aac`
- `0x140396b28`
- `0x140396ba8`
- `0x1403a5394`
- `0x1403a8450`
- `0x1403b330c`
- `0x1404063c4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14040650b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14040653b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406689`
- `ntoskrnl!ExFreePoolWithTag` at `0x1404066b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1404066dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14040670a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406739`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406761`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406a58`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406a85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406ab2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406ad9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406b06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406b35`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406b5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14040650b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14040653b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406689`
- `ntoskrnl!ExFreePoolWithTag` at `0x1404066b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1404066dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14040670a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406739`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406761`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406a58`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406a85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406ab2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406ad9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406b06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406b35`
- `ntoskrnl!ExFreePoolWithTag` at `0x140406b5d`
- `ntoskrnl!PsGetCurrentProcess` at `0x140406441`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404064be`
- `ntoskrnl!PsGetCurrentProcess` at `0x140406570`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404065cd`
- `ntoskrnl!PsGetCurrentProcess` at `0x140406639`
- `ntoskrnl!PsGetCurrentProcess` at `0x140406441`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404064be`
- `ntoskrnl!PsGetCurrentProcess` at `0x140406570`
- `ntoskrnl!PsGetCurrentProcess` at `0x1404065cd`
- `ntoskrnl!PsGetCurrentProcess` at `0x140406639`
- `watchdog!WdLogSingleEntry3` at `0x14040645e`
- `watchdog!WdLogSingleEntry3` at `0x1404064db`
- `watchdog!WdLogSingleEntry3` at `0x14040658d`
- `watchdog!WdLogSingleEntry3` at `0x1404065ea`
- `watchdog!WdLogSingleEntry3` at `0x140406657`
- `watchdog!WdLogSingleEntry3` at `0x14040645e`
- `watchdog!WdLogSingleEntry3` at `0x1404064db`
- `watchdog!WdLogSingleEntry3` at `0x14040658d`
- `watchdog!WdLogSingleEntry3` at `0x1404065ea`
- `watchdog!WdLogSingleEntry3` at `0x140406657`
- `watchdog!WdLogSingleEntry0` at `0x140406859`
- `watchdog!WdLogSingleEntry0` at `0x1404068b4`
- `watchdog!WdLogSingleEntry0` at `0x140406859`
- `watchdog!WdLogSingleEntry0` at `0x1404068b4`

## string_xrefs

- `0x1404068c5`: `ActualPostCompositionCount <= NumVidPnSources`
- `0x14040698e`: `Invalid allocation in CheckMPO cache`

## pseudocode

```c

```
