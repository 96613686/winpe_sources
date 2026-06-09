# DXGDEVICE::CheckMultiPlaneOverlaySupport3(uint,_D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3 * *,uint,_D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE * *,bool,int *,D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO *)

- ea: `0x140396c24`
- end: `0x140397c59`
- name: `?CheckMultiPlaneOverlaySupport3@DXGDEVICE@@QEAAJIPEAPEAU_D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3@@IPEAPEAU_D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE@@_NPEAHPEAUD3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO@@@Z`
- size: `4149`
- prototype: `__int64 __usercall@<rax>(DXGDEVICE *__hidden this@<rcx>, unsigned int@<edx>, struct _D3DKMT_CHECK_MULTIPLANE_OVERLAY_PLANE3 **@<r8>, unsigned int@<r9d>, struct _D3DKMT_MULTIPLANE_OVERLAY_POST_COMPOSITION_WITH_SOURCE **, bool, int *, struct D3DKMT_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO *)`
- caller_count: `4`
- callee_count: `25`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401d5590`
- `0x1402183a4`
- `0x140218588`
- `0x140395c50`

## callees

- `0x1400144ec`
- `0x1400150d0`
- `0x1400160e4`
- `0x1400161c8`
- `0x14001b890`
- `0x14001d070`
- `0x140040f34`
- `0x14004d2a4`
- `0x140069c94`
- `0x1400a0100`
- `0x14019547c`
- `0x1401f702c`
- `0x140311474`
- `0x140329f10`
- `0x14034056c`
- `0x140340858`
- `0x140340bd8`
- `0x14036f9f0`
- `0x14036fd90`
- `0x14038ef2c`
- `0x140393494`
- `0x140396c24`
- `0x14039eb70`
- `0x1403e8954`
- `0x1404063c4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140397155`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140397155`
- `ntoskrnl!ExFreePoolWithTag` at `0x140396d7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140396da2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140397bf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140397c1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140396d7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140396da2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140397bf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140397c1f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140397149`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140397149`
- `ntoskrnl!PsGetCurrentProcess` at `0x140396cdd`
- `ntoskrnl!PsGetCurrentProcess` at `0x140396d33`
- `ntoskrnl!PsGetCurrentProcess` at `0x140396cdd`
- `ntoskrnl!PsGetCurrentProcess` at `0x140396d33`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140397b74`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140397b74`
- `watchdog!WdLogSingleEntry4` at `0x14039737c`
- `watchdog!WdLogSingleEntry4` at `0x1403977e9`
- `watchdog!WdLogSingleEntry4` at `0x14039737c`
- `watchdog!WdLogSingleEntry4` at `0x1403977e9`
- `watchdog!WdLogSingleEntry2` at `0x140396e85`
- `watchdog!WdLogSingleEntry2` at `0x140396f70`
- `watchdog!WdLogSingleEntry2` at `0x140396ff7`
- `watchdog!WdLogSingleEntry2` at `0x140397014`
- `watchdog!WdLogSingleEntry2` at `0x1403973f7`
- `watchdog!WdLogSingleEntry2` at `0x14039788b`
- `watchdog!WdLogSingleEntry2` at `0x1403978c9`
- `watchdog!WdLogSingleEntry2` at `0x140396e85`
- `watchdog!WdLogSingleEntry2` at `0x140396f70`
- `watchdog!WdLogSingleEntry2` at `0x140396ff7`
- `watchdog!WdLogSingleEntry2` at `0x140397014`
- `watchdog!WdLogSingleEntry2` at `0x1403973f7`
- `watchdog!WdLogSingleEntry2` at `0x14039788b`
- `watchdog!WdLogSingleEntry2` at `0x1403978c9`
- `watchdog!WdLogSingleEntry3` at `0x140396cfb`
- `watchdog!WdLogSingleEntry3` at `0x140396d51`
- `watchdog!WdLogSingleEntry3` at `0x140397331`
- `watchdog!WdLogSingleEntry3` at `0x1403976eb`
- `watchdog!WdLogSingleEntry3` at `0x14039774e`
- `watchdog!WdLogSingleEntry3` at `0x1403977b6`
- `watchdog!WdLogSingleEntry3` at `0x14039786e`
- `watchdog!WdLogSingleEntry3` at `0x140396cfb`
- `watchdog!WdLogSingleEntry3` at `0x140396d51`
- `watchdog!WdLogSingleEntry3` at `0x140397331`
- `watchdog!WdLogSingleEntry3` at `0x1403976eb`
- `watchdog!WdLogSingleEntry3` at `0x14039774e`
- `watchdog!WdLogSingleEntry3` at `0x1403977b6`
- `watchdog!WdLogSingleEntry3` at `0x14039786e`
- `watchdog!WdLogSingleEntry0` at `0x140396dd1`
- `watchdog!WdLogSingleEntry0` at `0x1403970de`
- `watchdog!WdLogSingleEntry0` at `0x140396dd1`
- `watchdog!WdLogSingleEntry0` at `0x1403970de`
- `watchdog!WdLogSingleEntry1` at `0x140396ca4`
- `watchdog!WdLogSingleEntry1` at `0x140397039`
- `watchdog!WdLogSingleEntry1` at `0x140397453`
- `watchdog!WdLogSingleEntry1` at `0x140397712`
- `watchdog!WdLogSingleEntry1` at `0x140397848`
- `watchdog!WdLogSingleEntry1` at `0x140396ca4`
- `watchdog!WdLogSingleEntry1` at `0x140397039`
- `watchdog!WdLogSingleEntry1` at `0x140397453`
- `watchdog!WdLogSingleEntry1` at `0x140397712`
- `watchdog!WdLogSingleEntry1` at `0x140397848`

## string_xrefs

- `0x1403977c2`: `ret = 0x%I64x Context 0x%I64x Source rect is outside of allocation rect, index 0x%I64x`
- `0x14039775a`: `ret = 0x%I64x Context 0x%I64x Clip rect is outside of destination rect, index 0x%I64x`

## pseudocode

```c

```
