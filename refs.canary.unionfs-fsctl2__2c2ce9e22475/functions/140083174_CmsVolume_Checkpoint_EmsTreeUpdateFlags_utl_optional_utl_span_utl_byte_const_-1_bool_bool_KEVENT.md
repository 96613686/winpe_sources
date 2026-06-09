# CmsVolume::Checkpoint(EmsTreeUpdateFlags,utl::optional<utl::span<utl::byte const,-1>>,bool *,bool *,_KEVENT *)

- ea: `0x140083174`
- end: `0x140083eab`
- name: `?Checkpoint@CmsVolume@@QEAAJW4EmsTreeUpdateFlags@@V?$optional@V?$span@$$CBW4byte@utl@@$0?0@utl@@@utl@@PEA_N2PEAU_KEVENT@@@Z`
- size: `3383`
- prototype: `__int64 __usercall@<rax>(CmsVolume *this@<rcx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `48`
- tags: `installer_update`

## callers

- `0x1400823f8`
- `0x140082920`

## callees

- `0x140012b30`
- `0x1400146c0`
- `0x1400340e0`
- `0x14003a638`
- `0x140054d40`
- `0x14005f100`
- `0x140060b80`
- `0x1400710d0`
- `0x140072970`
- `0x14007e850`
- `0x14007fba0`
- `0x140081940`
- `0x140083174`
- `0x14009d1c0`
- `0x14009e308`
- `0x14009edc0`
- `0x1400acb90`
- `0x1400ad6b0`
- `0x1400b019c`
- `0x1400b4ab8`
- `0x1400bcf80`
- `0x1400bf698`
- `0x1400c4acc`
- `0x1400c59d8`
- `0x1400c6460`
- `0x1400c9080`
- `0x1400cd1d0`
- `0x1400ce6c8`
- `0x1400d8ed8`
- `0x140118914`
- `0x14012084c`
- `0x140120d6c`
- `0x140120e98`
- `0x140128268`
- `0x140128bc0`
- `0x140128c78`
- `0x140129000`
- `0x140129104`
- `0x140129174`
- `0x14012984c`
- `0x140129aec`
- `0x140129f10`
- `0x14012a958`
- `0x14012c708`
- `0x14013ff9c`
- `0x14016a954`
- `0x1401ea140`
- `0x1401ea660`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x1400837f1`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400837f1`
- `ntoskrnl!KeSetEvent` at `0x1400832f0`
- `ntoskrnl!KeSetEvent` at `0x140083dec`
- `ntoskrnl!KeSetEvent` at `0x140083e71`
- `ntoskrnl!KeSetEvent` at `0x1400832f0`
- `ntoskrnl!KeSetEvent` at `0x140083dec`
- `ntoskrnl!KeSetEvent` at `0x140083e71`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140083591`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140083591`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14008322b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14008322b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140083255`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400832b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140083255`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400832b2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400832dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140083332`
- `ntoskrnl!ExReleaseResourceLite` at `0x140083d4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140083e59`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400832dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140083332`
- `ntoskrnl!ExReleaseResourceLite` at `0x140083d4a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140083e59`
- `HAL!KeQueryPerformanceCounter` at `0x140083350`
- `HAL!KeQueryPerformanceCounter` at `0x140083c8b`
- `HAL!KeQueryPerformanceCounter` at `0x140083350`
- `HAL!KeQueryPerformanceCounter` at `0x140083c8b`

## pseudocode

```c

```
