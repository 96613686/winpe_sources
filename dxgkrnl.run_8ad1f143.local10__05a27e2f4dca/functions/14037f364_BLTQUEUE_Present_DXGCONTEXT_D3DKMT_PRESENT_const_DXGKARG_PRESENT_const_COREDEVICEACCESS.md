# BLTQUEUE::Present(DXGCONTEXT *,_D3DKMT_PRESENT const *,_DXGKARG_PRESENT const *,COREDEVICEACCESS *)

- ea: `0x14037f364`
- end: `0x140380003`
- name: `?Present@BLTQUEUE@@QEAAJPEAVDXGCONTEXT@@PEBU_D3DKMT_PRESENT@@PEBU_DXGKARG_PRESENT@@PEAVCOREDEVICEACCESS@@@Z`
- size: `3231`
- prototype: `__int64 __usercall@<rax>(BLTQUEUE *__hidden this@<rcx>, struct DXGCONTEXT *@<rdx>, const struct _D3DKMT_PRESENT *@<r8>, const struct _DXGKARG_PRESENT *@<r9>, struct COREDEVICEACCESS *)`
- caller_count: `1`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x14037f2a8`

## callees

- `0x140012cd4`
- `0x140013a20`
- `0x1400146ac`
- `0x140015290`
- `0x140016388`
- `0x1400198d8`
- `0x14001ab00`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001c450`
- `0x14001d214`
- `0x140037ac0`
- `0x140046258`
- `0x1400593e4`
- `0x1400674c4`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x1401a3f84`
- `0x1401e76e0`
- `0x140292838`
- `0x140308cd0`
- `0x14032a5c4`
- `0x14032e980`
- `0x14037e708`
- `0x14037ed3c`
- `0x14037f364`
- `0x14038056c`
- `0x140380634`
- `0x140380b20`
- `0x140380bfc`
- `0x140380ccc`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14037ffb3`
- `ntoskrnl!KeSetEvent` at `0x14037ffb3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14037f5ad`
- `ntoskrnl!KeWaitForSingleObject` at `0x14037f684`
- `ntoskrnl!KeWaitForSingleObject` at `0x14037f917`
- `ntoskrnl!KeWaitForSingleObject` at `0x14037f5ad`
- `ntoskrnl!KeWaitForSingleObject` at `0x14037f684`
- `ntoskrnl!KeWaitForSingleObject` at `0x14037f917`
- `ntoskrnl!KeReleaseMutex` at `0x14037f5c6`
- `ntoskrnl!KeReleaseMutex` at `0x14037f69c`
- `ntoskrnl!KeReleaseMutex` at `0x14037f94e`
- `ntoskrnl!KeReleaseMutex` at `0x14037f5c6`
- `ntoskrnl!KeReleaseMutex` at `0x14037f69c`
- `ntoskrnl!KeReleaseMutex` at `0x14037f94e`
- `HAL!KeQueryPerformanceCounter` at `0x14037ff94`
- `HAL!KeQueryPerformanceCounter` at `0x14037ff94`
- `watchdog!WdLogSingleEntry2` at `0x14037f4a9`
- `watchdog!WdLogSingleEntry2` at `0x14037f5eb`
- `watchdog!WdLogSingleEntry2` at `0x14037f6d2`
- `watchdog!WdLogSingleEntry2` at `0x14037f761`
- `watchdog!WdLogSingleEntry2` at `0x14037f7c2`
- `watchdog!WdLogSingleEntry2` at `0x14037f8a4`
- `watchdog!WdLogSingleEntry2` at `0x14037f4a9`
- `watchdog!WdLogSingleEntry2` at `0x14037f5eb`
- `watchdog!WdLogSingleEntry2` at `0x14037f6d2`
- `watchdog!WdLogSingleEntry2` at `0x14037f761`
- `watchdog!WdLogSingleEntry2` at `0x14037f7c2`
- `watchdog!WdLogSingleEntry2` at `0x14037f8a4`
- `watchdog!WdLogSingleEntry3` at `0x14037fe24`
- `watchdog!WdLogSingleEntry3` at `0x14037fea0`
- `watchdog!WdLogSingleEntry3` at `0x14037fe24`
- `watchdog!WdLogSingleEntry3` at `0x14037fea0`
- `watchdog!WdLogSingleEntry0` at `0x14037f9a5`
- `watchdog!WdLogSingleEntry0` at `0x14037fa7c`
- `watchdog!WdLogSingleEntry0` at `0x14037fb44`
- `watchdog!WdLogSingleEntry0` at `0x14037f9a5`
- `watchdog!WdLogSingleEntry0` at `0x14037fa7c`
- `watchdog!WdLogSingleEntry0` at `0x14037fb44`

## string_xrefs

- `0x14037fedb`: `Exception when accessing command buffer 0x%I64x on 0x%I64x for 0x%I64x.`

## pseudocode

```c

```
