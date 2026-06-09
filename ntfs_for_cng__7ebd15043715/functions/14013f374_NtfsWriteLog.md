# NtfsWriteLog

- ea: `0x14013f374`
- end: `0x140140319`
- name: `NtfsWriteLog`
- size: `4005`
- prototype: `union _LARGE_INTEGER __fastcall(__int64, __int64, void *, int, __int64 *, int, int, __int64 *, unsigned int, __int64, __int16, __int16, int)`
- caller_count: `69`
- callee_count: `20`
- tags: ``

## callers

- `0x1400285c0`
- `0x140037854`
- `0x14004ed48`
- `0x1400bd6b4`
- `0x1400c0ca8`
- `0x1400c2bd8`
- `0x1400c3090`
- `0x1400cf580`
- `0x1400deecc`
- `0x1400df084`
- `0x1400e7f78`
- `0x1400ec444`
- `0x1400ec594`
- `0x1400edd1c`
- `0x1400ede98`
- `0x1400edfe0`
- `0x1400ee0f8`
- `0x1400ee2b4`
- `0x1400ef0a8`
- `0x14011d2d0`
- `0x140129fb0`
- `0x140131620`
- `0x14013c2d0`
- `0x14013cde0`
- `0x14013f374`
- `0x140140660`
- `0x140142c10`
- `0x1401436e0`
- `0x14014c7e0`
- `0x14014d840`
- `0x14014df80`
- `0x14014ecf0`
- `0x140151d54`
- `0x14015283c`
- `0x14015318c`
- `0x1401543cc`
- `0x140155070`
- `0x140155bf0`
- `0x140156080`
- `0x140157610`
- `0x1401578a0`
- `0x140158af0`
- `0x14015a570`
- `0x14015af40`
- `0x14015b8b0`
- `0x14015d080`
- `0x14015d644`
- `0x14015e3f4`
- `0x140164e5c`
- `0x140165278`

## callees

- `0x1400054e8`
- `0x140007ea0`
- `0x14000c290`
- `0x140021020`
- `0x1400224cc`
- `0x1400226f0`
- `0x140022a00`
- `0x14003c34c`
- `0x1400410a8`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x14012e1f0`
- `0x14012e4f0`
- `0x14013f374`
- `0x1401611e0`
- `0x1401620c0`
- `0x1401b2830`
- `0x1401e72e8`
- `0x140250104`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1402a71e0`
- `ntoskrnl!KeSetEvent` at `0x1402c8526`
- `ntoskrnl!KeSetEvent` at `0x1402a71e0`
- `ntoskrnl!KeSetEvent` at `0x1402c8526`
- `ntoskrnl!ExQueueWorkItem` at `0x14013fcd9`
- `ntoskrnl!ExQueueWorkItem` at `0x14013fcd9`
- `ntoskrnl!IoGetActivityIdThread` at `0x14013fc75`
- `ntoskrnl!IoGetActivityIdThread` at `0x14013fc75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140308`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a725e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140140308`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a725e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14014014e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14014014e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14013f4c8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14013fd8b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401400f7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402a7103`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402a7192`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c84da`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14013f4c8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14013fd8b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401400f7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402a7103`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402a7192`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402c84da`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013f589`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013fa94`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013fe51`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013fec7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140140092`
- `ntoskrnl!ExReleaseResourceLite` at `0x140140254`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401402da`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401402f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a714f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a7173`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a7208`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a7222`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a723c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013f589`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013fa94`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013fe51`
- `ntoskrnl!ExReleaseResourceLite` at `0x14013fec7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140140092`
- `ntoskrnl!ExReleaseResourceLite` at `0x140140254`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401402da`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401402f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a714f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a7173`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a7208`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a7222`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a723c`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14013fac8`
- `ntoskrnl!CcSetDirtyPinnedData` at `0x14013fac8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14013f925`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14013f925`

## pseudocode

```c

```
