# DXGDEVICE::CreateStandardAllocation(_D3DKM_CREATESTANDARDALLOCATION *,COREDEVICEACCESS *)

- ea: `0x1403c36ac`
- end: `0x1403c4318`
- name: `?CreateStandardAllocation@DXGDEVICE@@QEAAJPEAU_D3DKM_CREATESTANDARDALLOCATION@@PEAVCOREDEVICEACCESS@@@Z`
- size: `3180`
- prototype: `__int64 __fastcall(DXGDEVICE *__hidden this, struct _D3DKM_CREATESTANDARDALLOCATION *, struct COREDEVICEACCESS *)`
- caller_count: `9`
- callee_count: `20`
- tags: ``

## callers

- `0x1401abe40`
- `0x1401f1084`
- `0x140218d44`
- `0x140231100`
- `0x140301f60`
- `0x140319248`
- `0x14031bb50`
- `0x1403c3680`
- `0x1403db9d8`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x14001a7d4`
- `0x14001ab20`
- `0x14001b890`
- `0x14001d070`
- `0x140033bb0`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0240`
- `0x1400a0540`
- `0x14020d670`
- `0x14031de8c`
- `0x140323854`
- `0x140327c10`
- `0x140329000`
- `0x14034599c`
- `0x140377040`
- `0x1403c36ac`
- `0x1403c4320`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c3e6f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c3e6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403c39c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403c42ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403c39c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403c42ca`
- `ntoskrnl!ExAllocatePool2` at `0x1403c37c9`
- `ntoskrnl!ExAllocatePool2` at `0x1403c37c9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403c3e63`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403c3e63`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1403c3e84`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1403c3e84`
- `watchdog!WdLogSingleEntry4` at `0x1403c3bee`
- `watchdog!WdLogSingleEntry4` at `0x1403c3bee`
- `watchdog!WdLogSingleEntry2` at `0x1403c3858`
- `watchdog!WdLogSingleEntry2` at `0x1403c38c6`
- `watchdog!WdLogSingleEntry2` at `0x1403c3858`
- `watchdog!WdLogSingleEntry2` at `0x1403c38c6`
- `watchdog!WdLogSingleEntry3` at `0x1403c3924`
- `watchdog!WdLogSingleEntry3` at `0x1403c3966`
- `watchdog!WdLogSingleEntry3` at `0x1403c3a0d`
- `watchdog!WdLogSingleEntry3` at `0x1403c3bb6`
- `watchdog!WdLogSingleEntry3` at `0x1403c3c51`
- `watchdog!WdLogSingleEntry3` at `0x1403c3f4d`
- `watchdog!WdLogSingleEntry3` at `0x1403c3f8d`
- `watchdog!WdLogSingleEntry3` at `0x1403c426d`
- `watchdog!WdLogSingleEntry3` at `0x1403c3924`
- `watchdog!WdLogSingleEntry3` at `0x1403c3966`
- `watchdog!WdLogSingleEntry3` at `0x1403c3a0d`
- `watchdog!WdLogSingleEntry3` at `0x1403c3bb6`
- `watchdog!WdLogSingleEntry3` at `0x1403c3c51`
- `watchdog!WdLogSingleEntry3` at `0x1403c3f4d`
- `watchdog!WdLogSingleEntry3` at `0x1403c3f8d`
- `watchdog!WdLogSingleEntry3` at `0x1403c426d`
- `watchdog!WdLogSingleEntry0` at `0x1403c3b2b`
- `watchdog!WdLogSingleEntry0` at `0x1403c3e03`
- `watchdog!WdLogSingleEntry0` at `0x1403c3ff2`
- `watchdog!WdLogSingleEntry0` at `0x1403c4048`
- `watchdog!WdLogSingleEntry0` at `0x1403c40f2`
- `watchdog!WdLogSingleEntry0` at `0x1403c4140`
- `watchdog!WdLogSingleEntry0` at `0x1403c3b2b`
- `watchdog!WdLogSingleEntry0` at `0x1403c3e03`
- `watchdog!WdLogSingleEntry0` at `0x1403c3ff2`
- `watchdog!WdLogSingleEntry0` at `0x1403c4048`
- `watchdog!WdLogSingleEntry0` at `0x1403c40f2`
- `watchdog!WdLogSingleEntry0` at `0x1403c4140`

## string_xrefs

- `0x1403c3f9d`: `Device 0x%I64x: created standard allocation but the allocation handle (0x%I64x) lookup failed!, returning 0x%I64x`
- `0x1403c3b3c`: `!pCreateStandardAllocation->Flags.OpenCrossAdapter || !pCreateStandardAllocation->Flags.Primary`
- `0x1403c3f63`: `Device 0x%I64x: Driver did not create CPUVisible allocation for standard allocation type 0x%I64x, returning 0x%I64x`
- `0x1403c4003`: `CreateAlloc.hResource != NULL`

## pseudocode

```c

```
