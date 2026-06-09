# DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendLock2(DXGPROCESS *,DXGDEVICE *,_D3DKMT_LOCK2 *,uchar,uint,uint)

- ea: `0x14035e3e0`
- end: `0x14035ebca`
- name: `?VmBusSendLock2@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAJPEAVDXGPROCESS@@PEAVDXGDEVICE@@PEAU_D3DKMT_LOCK2@@EII@Z`
- size: `2026`
- prototype: `__int64 __usercall@<rax>(DXG_GUEST_VIRTUALGPU_VMBUS *__hidden this@<rcx>, struct DXGPROCESS *@<rdx>, struct DXGDEVICE *@<r8>, struct _D3DKMT_LOCK2 *@<r9>, unsigned __int8, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `16`
- tags: ``

## callers

- `0x140308cd0`
- `0x14032fde8`
- `0x14039aac0`
- `0x1403c6680`

## callees

- `0x140012540`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001cd10`
- `0x14001d1a0`
- `0x140037ac0`
- `0x140062800`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x14019af20`
- `0x14021041c`
- `0x1402994b4`
- `0x14032e980`
- `0x14032fd70`
- `0x14035e3e0`
- `0x14035f600`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035e4e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035e4e1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14035e4d5`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14035e4d5`
- `ntoskrnl!IoAllocateMdl` at `0x14035e91b`
- `ntoskrnl!IoAllocateMdl` at `0x14035e91b`
- `ntoskrnl!IoFreeMdl` at `0x14035eb1d`
- `ntoskrnl!IoFreeMdl` at `0x14035eb1d`
- `ntoskrnl!MmRotatePhysicalView` at `0x14035e9ba`
- `ntoskrnl!MmRotatePhysicalView` at `0x14035e9ba`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14035e64c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14035e64c`
- `ntoskrnl!MmUnmapLockedPages` at `0x14035eaa2`
- `ntoskrnl!MmUnmapLockedPages` at `0x14035eaa2`
- `watchdog!WdLogSingleEntry2` at `0x14035e8e8`
- `watchdog!WdLogSingleEntry2` at `0x14035e940`
- `watchdog!WdLogSingleEntry2` at `0x14035e8e8`
- `watchdog!WdLogSingleEntry2` at `0x14035e940`
- `watchdog!WdLogSingleEntry3` at `0x14035e56b`
- `watchdog!WdLogSingleEntry3` at `0x14035e56b`
- `watchdog!WdLogSingleEntry0` at `0x14035e478`
- `watchdog!WdLogSingleEntry0` at `0x14035e50e`
- `watchdog!WdLogSingleEntry0` at `0x14035e478`
- `watchdog!WdLogSingleEntry0` at `0x14035e50e`
- `watchdog!WdLogSingleEntry1` at `0x14035e9dc`
- `watchdog!WdLogSingleEntry1` at `0x14035ea37`
- `watchdog!WdLogSingleEntry1` at `0x14035eb38`
- `watchdog!WdLogSingleEntry1` at `0x14035e9dc`
- `watchdog!WdLogSingleEntry1` at `0x14035ea37`
- `watchdog!WdLogSingleEntry1` at `0x14035eb38`

## pseudocode

```c

```
