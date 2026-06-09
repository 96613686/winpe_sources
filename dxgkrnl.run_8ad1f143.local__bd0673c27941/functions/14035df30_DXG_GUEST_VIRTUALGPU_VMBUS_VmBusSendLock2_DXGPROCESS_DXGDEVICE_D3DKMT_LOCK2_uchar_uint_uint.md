# DXG_GUEST_VIRTUALGPU_VMBUS::VmBusSendLock2(DXGPROCESS *,DXGDEVICE *,_D3DKMT_LOCK2 *,uchar,uint,uint)

- ea: `0x14035df30`
- end: `0x14035e71a`
- name: `?VmBusSendLock2@DXG_GUEST_VIRTUALGPU_VMBUS@@QEAAJPEAVDXGPROCESS@@PEAVDXGDEVICE@@PEAU_D3DKMT_LOCK2@@EII@Z`
- size: `2026`
- prototype: `__int64 __usercall@<rax>(DXG_GUEST_VIRTUALGPU_VMBUS *__hidden this@<rcx>, struct DXGPROCESS *@<rdx>, struct DXGDEVICE *@<r8>, struct _D3DKMT_LOCK2 *@<r9>, unsigned __int8, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `16`
- tags: ``

## callers

- `0x140301f60`
- `0x140329078`
- `0x140399ce0`
- `0x1403c72d0`

## callees

- `0x140012380`
- `0x14001ab20`
- `0x14001b890`
- `0x14001cbe0`
- `0x14001d070`
- `0x1400378f0`
- `0x140062450`
- `0x1400a0100`
- `0x1400a01e0`
- `0x140196f20`
- `0x14020ddcc`
- `0x140292b54`
- `0x140327c10`
- `0x140329000`
- `0x14035df30`
- `0x14035f150`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035e031`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14035e031`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14035e025`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14035e025`
- `ntoskrnl!IoAllocateMdl` at `0x14035e46b`
- `ntoskrnl!IoAllocateMdl` at `0x14035e46b`
- `ntoskrnl!IoFreeMdl` at `0x14035e66d`
- `ntoskrnl!IoFreeMdl` at `0x14035e66d`
- `ntoskrnl!MmRotatePhysicalView` at `0x14035e50a`
- `ntoskrnl!MmRotatePhysicalView` at `0x14035e50a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14035e19c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14035e19c`
- `ntoskrnl!MmUnmapLockedPages` at `0x14035e5f2`
- `ntoskrnl!MmUnmapLockedPages` at `0x14035e5f2`
- `watchdog!WdLogSingleEntry2` at `0x14035e438`
- `watchdog!WdLogSingleEntry2` at `0x14035e490`
- `watchdog!WdLogSingleEntry2` at `0x14035e438`
- `watchdog!WdLogSingleEntry2` at `0x14035e490`
- `watchdog!WdLogSingleEntry3` at `0x14035e0bb`
- `watchdog!WdLogSingleEntry3` at `0x14035e0bb`
- `watchdog!WdLogSingleEntry0` at `0x14035dfc8`
- `watchdog!WdLogSingleEntry0` at `0x14035e05e`
- `watchdog!WdLogSingleEntry0` at `0x14035dfc8`
- `watchdog!WdLogSingleEntry0` at `0x14035e05e`
- `watchdog!WdLogSingleEntry1` at `0x14035e52c`
- `watchdog!WdLogSingleEntry1` at `0x14035e587`
- `watchdog!WdLogSingleEntry1` at `0x14035e688`
- `watchdog!WdLogSingleEntry1` at `0x14035e52c`
- `watchdog!WdLogSingleEntry1` at `0x14035e587`
- `watchdog!WdLogSingleEntry1` at `0x14035e688`

## pseudocode

```c

```
