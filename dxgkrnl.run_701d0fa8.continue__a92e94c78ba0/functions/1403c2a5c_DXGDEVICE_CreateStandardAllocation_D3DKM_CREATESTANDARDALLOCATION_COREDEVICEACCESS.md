# DXGDEVICE::CreateStandardAllocation(_D3DKM_CREATESTANDARDALLOCATION *,COREDEVICEACCESS *)

- ea: `0x1403c2a5c`
- end: `0x1403c36c8`
- name: `?CreateStandardAllocation@DXGDEVICE@@QEAAJPEAU_D3DKM_CREATESTANDARDALLOCATION@@PEAVCOREDEVICEACCESS@@@Z`
- size: `3180`
- prototype: `__int64 __fastcall(DXGDEVICE *__hidden this, struct _D3DKM_CREATESTANDARDALLOCATION *, struct COREDEVICEACCESS *)`
- caller_count: `9`
- callee_count: `20`
- tags: ``

## callers

- `0x1401f3454`
- `0x14021b394`
- `0x140233c10`
- `0x140280ed0`
- `0x140308cd0`
- `0x14031ffb8`
- `0x1403228c0`
- `0x1403c2a30`
- `0x1403dbdf8`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x14001a874`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001d1a0`
- `0x140033d80`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x14020fcc0`
- `0x140324bfc`
- `0x14032a5c4`
- `0x14032e980`
- `0x14032fd70`
- `0x140377080`
- `0x14038818c`
- `0x1403c2a5c`
- `0x1403c36d0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c321f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1403c321f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403c2d73`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403c367a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403c2d73`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403c367a`
- `ntoskrnl!ExAllocatePool2` at `0x1403c2b79`
- `ntoskrnl!ExAllocatePool2` at `0x1403c2b79`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403c3213`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1403c3213`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1403c3234`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1403c3234`
- `watchdog!WdLogSingleEntry4` at `0x1403c2f9e`
- `watchdog!WdLogSingleEntry4` at `0x1403c2f9e`
- `watchdog!WdLogSingleEntry2` at `0x1403c2c08`
- `watchdog!WdLogSingleEntry2` at `0x1403c2c76`
- `watchdog!WdLogSingleEntry2` at `0x1403c2c08`
- `watchdog!WdLogSingleEntry2` at `0x1403c2c76`
- `watchdog!WdLogSingleEntry3` at `0x1403c2cd4`
- `watchdog!WdLogSingleEntry3` at `0x1403c2d16`
- `watchdog!WdLogSingleEntry3` at `0x1403c2dbd`
- `watchdog!WdLogSingleEntry3` at `0x1403c2f66`
- `watchdog!WdLogSingleEntry3` at `0x1403c3001`
- `watchdog!WdLogSingleEntry3` at `0x1403c32fd`
- `watchdog!WdLogSingleEntry3` at `0x1403c333d`
- `watchdog!WdLogSingleEntry3` at `0x1403c361d`
- `watchdog!WdLogSingleEntry3` at `0x1403c2cd4`
- `watchdog!WdLogSingleEntry3` at `0x1403c2d16`
- `watchdog!WdLogSingleEntry3` at `0x1403c2dbd`
- `watchdog!WdLogSingleEntry3` at `0x1403c2f66`
- `watchdog!WdLogSingleEntry3` at `0x1403c3001`
- `watchdog!WdLogSingleEntry3` at `0x1403c32fd`
- `watchdog!WdLogSingleEntry3` at `0x1403c333d`
- `watchdog!WdLogSingleEntry3` at `0x1403c361d`
- `watchdog!WdLogSingleEntry0` at `0x1403c2edb`
- `watchdog!WdLogSingleEntry0` at `0x1403c31b3`
- `watchdog!WdLogSingleEntry0` at `0x1403c33a2`
- `watchdog!WdLogSingleEntry0` at `0x1403c33f8`
- `watchdog!WdLogSingleEntry0` at `0x1403c34a2`
- `watchdog!WdLogSingleEntry0` at `0x1403c34f0`
- `watchdog!WdLogSingleEntry0` at `0x1403c2edb`
- `watchdog!WdLogSingleEntry0` at `0x1403c31b3`
- `watchdog!WdLogSingleEntry0` at `0x1403c33a2`
- `watchdog!WdLogSingleEntry0` at `0x1403c33f8`
- `watchdog!WdLogSingleEntry0` at `0x1403c34a2`
- `watchdog!WdLogSingleEntry0` at `0x1403c34f0`

## string_xrefs

- `0x1403c334d`: `Device 0x%I64x: created standard allocation but the allocation handle (0x%I64x) lookup failed!, returning 0x%I64x`
- `0x1403c2eec`: `!pCreateStandardAllocation->Flags.OpenCrossAdapter || !pCreateStandardAllocation->Flags.Primary`
- `0x1403c3313`: `Device 0x%I64x: Driver did not create CPUVisible allocation for standard allocation type 0x%I64x, returning 0x%I64x`
- `0x1403c33b3`: `CreateAlloc.hResource != NULL`

## pseudocode

```c

```
