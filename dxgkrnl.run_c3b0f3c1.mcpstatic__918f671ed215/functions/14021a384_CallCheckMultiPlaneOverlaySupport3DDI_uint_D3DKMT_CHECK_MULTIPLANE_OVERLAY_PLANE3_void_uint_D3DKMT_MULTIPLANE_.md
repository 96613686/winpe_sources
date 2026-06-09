# CallCheckMultiPlaneOverlaySupport3DDI(uint,_D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3 * *,void * *,uint,_D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE * *,ADAPTER_DISPLAY *,int *,D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO *)

- ea: `0x14021a384`
- end: `0x14021a9ed`
- name: `?CallCheckMultiPlaneOverlaySupport3DDI@@YAJIPEAPEAU_D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3@@PEAPEAXIPEAPEAU_D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE@@PEAVADAPTER_DISPLAY@@PEAHPEAUD3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO@@@Z`
- size: `1641`
- prototype: `__int64 __fastcall(__int64, struct _D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3 **, void **, unsigned int, struct _D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE **, struct ADAPTER_DISPLAY *, int *, struct DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO::$3235B0AF7BF3D9B607A1C4FD103E9694::$7E5D53739D5A0755634D9029F4E2827E *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140405714`

## callees

- `0x1400a0bd0`
- `0x1400a1000`
- `0x14021a384`
- `0x1403efb7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14021a6b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a6d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a700`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a72c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a938`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a961`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a988`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a9b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a6b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a6d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a700`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a72c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a938`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a961`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a988`
- `ntoskrnl!ExFreePoolWithTag` at `0x14021a9b4`
- `ntoskrnl!ExAllocatePool2` at `0x14021a436`
- `ntoskrnl!ExAllocatePool2` at `0x14021a4ea`
- `ntoskrnl!ExAllocatePool2` at `0x14021a5b5`
- `ntoskrnl!ExAllocatePool2` at `0x14021a614`
- `ntoskrnl!ExAllocatePool2` at `0x14021a436`
- `ntoskrnl!ExAllocatePool2` at `0x14021a4ea`
- `ntoskrnl!ExAllocatePool2` at `0x14021a5b5`
- `ntoskrnl!ExAllocatePool2` at `0x14021a614`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021a47e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021a529`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021a664`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021a47e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021a529`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021a664`
- `watchdog!WdLogSingleEntry3` at `0x14021a49a`
- `watchdog!WdLogSingleEntry3` at `0x14021a545`
- `watchdog!WdLogSingleEntry3` at `0x14021a682`
- `watchdog!WdLogSingleEntry3` at `0x14021a49a`
- `watchdog!WdLogSingleEntry3` at `0x14021a545`
- `watchdog!WdLogSingleEntry3` at `0x14021a682`

## pseudocode

```c

```
