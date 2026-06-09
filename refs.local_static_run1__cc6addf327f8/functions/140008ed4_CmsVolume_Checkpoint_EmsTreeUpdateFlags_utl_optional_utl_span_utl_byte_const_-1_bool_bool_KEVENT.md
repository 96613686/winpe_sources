# CmsVolume::Checkpoint(EmsTreeUpdateFlags,utl::optional<utl::span<utl::byte const,-1>>,bool *,bool *,_KEVENT *)

- ea: `0x140008ed4`
- end: `0x140009b63`
- name: `?Checkpoint@CmsVolume@@QEAAJW4EmsTreeUpdateFlags@@V?$optional@V?$span@$$CBW4byte@utl@@$0?0@utl@@@utl@@PEA_N2PEAU_KEVENT@@@Z`
- size: `3215`
- prototype: `__int64 __usercall@<rax>(CmsVolume *this@<rcx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `43`
- tags: `installer_update`

## callers

- `0x140008678`
- `0x140008860`

## callees

- `0x140008ed4`
- `0x140014750`
- `0x1400463d0`
- `0x140047400`
- `0x140049050`
- `0x14005c060`
- `0x14006caf0`
- `0x140076da0`
- `0x1400813e4`
- `0x140088930`
- `0x140099a10`
- `0x1400a6704`
- `0x1400a7d30`
- `0x1400a8ac0`
- `0x1400aac78`
- `0x1400abbfc`
- `0x1400b15e4`
- `0x1400c26b4`
- `0x1400cbe48`
- `0x1400cc50c`
- `0x1400cd338`
- `0x1400cf828`
- `0x1400d2eb4`
- `0x1400d3e44`
- `0x14011de14`
- `0x140126378`
- `0x140126784`
- `0x1401268b0`
- `0x14012df80`
- `0x14012ed78`
- `0x140130b28`
- `0x140144be8`
- `0x140144ca0`
- `0x140145028`
- `0x14014512c`
- `0x14014519c`
- `0x14014586c`
- `0x140145a74`
- `0x140145efc`
- `0x140147c6c`
- `0x140174b7c`
- `0x1401f4400`
- `0x1401f4920`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x140009550`
- `ntoskrnl!IoGetActivityIdThread` at `0x140009550`
- `ntoskrnl!KeSetEvent` at `0x14000904f`
- `ntoskrnl!KeSetEvent` at `0x140009aa4`
- `ntoskrnl!KeSetEvent` at `0x140009b29`
- `ntoskrnl!KeSetEvent` at `0x14000904f`
- `ntoskrnl!KeSetEvent` at `0x140009aa4`
- `ntoskrnl!KeSetEvent` at `0x140009b29`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400092f0`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400092f0`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140008f8b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140008f8b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008fb5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009011`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008fb5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009011`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000903b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009091`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009a0c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009b11`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000903b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009091`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009a0c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140009b11`
- `HAL!KeQueryPerformanceCounter` at `0x1400090af`
- `HAL!KeQueryPerformanceCounter` at `0x14000994d`
- `HAL!KeQueryPerformanceCounter` at `0x1400090af`
- `HAL!KeQueryPerformanceCounter` at `0x14000994d`

## pseudocode

```c

```
