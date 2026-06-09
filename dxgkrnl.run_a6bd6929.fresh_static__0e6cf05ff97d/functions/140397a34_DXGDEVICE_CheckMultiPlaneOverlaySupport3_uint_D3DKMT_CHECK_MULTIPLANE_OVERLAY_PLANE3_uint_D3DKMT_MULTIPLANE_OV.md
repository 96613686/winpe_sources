# DXGDEVICE::CheckMultiPlaneOverlaySupport3(uint,_D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3 * *,uint,_D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE * *,bool,int *,D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO *)

- ea: `0x140397a34`
- end: `0x140398a69`
- name: `?CheckMultiPlaneOverlaySupport3@DXGDEVICE@@QEAAJIPEAPEAU_D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3@@IPEAPEAU_D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE@@_NPEAHPEAUD3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO@@@Z`
- size: `4149`
- prototype: `__int64 __fastcall(ADAPTER_RENDER **this, unsigned int, struct _D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3 **, unsigned int, struct _D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE **, bool, int *, struct D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO *)`
- caller_count: `4`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401d8190`
- `0x14021a9f4`
- `0x14021abd8`
- `0x140396a60`

## callees

- `0x1400146ac`
- `0x140015290`
- `0x1400162a4`
- `0x140016388`
- `0x14001b9c0`
- `0x14001d1a0`
- `0x140041194`
- `0x14004d4a4`
- `0x14006a1f4`
- `0x1400a0bd0`
- `0x14019947c`
- `0x1401f940c`
- `0x1403181e4`
- `0x140330c80`
- `0x14036fa30`
- `0x14036fdd0`
- `0x14038dffc`
- `0x140392428`
- `0x1403929a0`
- `0x140393c6c`
- `0x140393f58`
- `0x140397a34`
- `0x14039f950`
- `0x1403e8c84`
- `0x140405714`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140397f65`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140397f65`
- `ntoskrnl!ExFreePoolWithTag` at `0x140397b8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140397bb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140398a00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140398a2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140397b8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140397bb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140398a00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140398a2f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140397f59`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140397f59`
- `ntoskrnl!PsGetCurrentProcess` at `0x140397aed`
- `ntoskrnl!PsGetCurrentProcess` at `0x140397b43`
- `ntoskrnl!PsGetCurrentProcess` at `0x140397aed`
- `ntoskrnl!PsGetCurrentProcess` at `0x140397b43`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140398984`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140398984`
- `watchdog!WdLogSingleEntry4` at `0x14039818c`
- `watchdog!WdLogSingleEntry4` at `0x1403985f9`
- `watchdog!WdLogSingleEntry4` at `0x14039818c`
- `watchdog!WdLogSingleEntry4` at `0x1403985f9`
- `watchdog!WdLogSingleEntry2` at `0x140397c95`
- `watchdog!WdLogSingleEntry2` at `0x140397d80`
- `watchdog!WdLogSingleEntry2` at `0x140397e07`
- `watchdog!WdLogSingleEntry2` at `0x140397e24`
- `watchdog!WdLogSingleEntry2` at `0x140398207`
- `watchdog!WdLogSingleEntry2` at `0x14039869b`
- `watchdog!WdLogSingleEntry2` at `0x1403986d9`
- `watchdog!WdLogSingleEntry2` at `0x140397c95`
- `watchdog!WdLogSingleEntry2` at `0x140397d80`
- `watchdog!WdLogSingleEntry2` at `0x140397e07`
- `watchdog!WdLogSingleEntry2` at `0x140397e24`
- `watchdog!WdLogSingleEntry2` at `0x140398207`
- `watchdog!WdLogSingleEntry2` at `0x14039869b`
- `watchdog!WdLogSingleEntry2` at `0x1403986d9`
- `watchdog!WdLogSingleEntry3` at `0x140397b0b`
- `watchdog!WdLogSingleEntry3` at `0x140397b61`
- `watchdog!WdLogSingleEntry3` at `0x140398141`
- `watchdog!WdLogSingleEntry3` at `0x1403984fb`
- `watchdog!WdLogSingleEntry3` at `0x14039855e`
- `watchdog!WdLogSingleEntry3` at `0x1403985c6`
- `watchdog!WdLogSingleEntry3` at `0x14039867e`
- `watchdog!WdLogSingleEntry3` at `0x140397b0b`
- `watchdog!WdLogSingleEntry3` at `0x140397b61`
- `watchdog!WdLogSingleEntry3` at `0x140398141`
- `watchdog!WdLogSingleEntry3` at `0x1403984fb`
- `watchdog!WdLogSingleEntry3` at `0x14039855e`
- `watchdog!WdLogSingleEntry3` at `0x1403985c6`
- `watchdog!WdLogSingleEntry3` at `0x14039867e`
- `watchdog!WdLogSingleEntry0` at `0x140397be1`
- `watchdog!WdLogSingleEntry0` at `0x140397eee`
- `watchdog!WdLogSingleEntry0` at `0x140397be1`
- `watchdog!WdLogSingleEntry0` at `0x140397eee`
- `watchdog!WdLogSingleEntry1` at `0x140397ab4`
- `watchdog!WdLogSingleEntry1` at `0x140397e49`
- `watchdog!WdLogSingleEntry1` at `0x140398263`
- `watchdog!WdLogSingleEntry1` at `0x140398522`
- `watchdog!WdLogSingleEntry1` at `0x140398658`
- `watchdog!WdLogSingleEntry1` at `0x140397ab4`
- `watchdog!WdLogSingleEntry1` at `0x140397e49`
- `watchdog!WdLogSingleEntry1` at `0x140398263`
- `watchdog!WdLogSingleEntry1` at `0x140398522`
- `watchdog!WdLogSingleEntry1` at `0x140398658`

## string_xrefs

- `0x14039856a`: `ret = 0x%I64x Context 0x%I64x Clip rect is outside of destination rect, index 0x%I64x`
- `0x1403985d2`: `ret = 0x%I64x Context 0x%I64x Source rect is outside of allocation rect, index 0x%I64x`

## pseudocode

```c

```
