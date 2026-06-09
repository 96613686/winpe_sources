# ndisOpenAdapterLegacyProtocol(int *,int *,void * *,uint *,_NDIS_MEDIUM *,uint,void *,void *,_UNICODE_STRING *,uint,_STRING *,int *)

- ea: `0x1400b6320`
- end: `0x1400b6c2d`
- name: `?ndisOpenAdapterLegacyProtocol@@YAXPEAH0PEAPEAXPEAIPEAW4_NDIS_MEDIUM@@IPEAX4PEAU_UNICODE_STRING@@IPEAU_STRING@@0@Z`
- size: `2317`
- prototype: `void __usercall(int *@<rcx>, int *@<rdx>, void **@<r8>, unsigned int *@<r9>, enum _NDIS_MEDIUM *, unsigned int, KIRQL NewIrql, void *, struct _UNICODE_STRING *, unsigned int, struct _STRING *, int *)`
- caller_count: `2`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x14016a620`
- `0x140175440`

## callees

- `0x140015280`
- `0x14001cc80`
- `0x14001cf50`
- `0x14002b980`
- `0x140036a70`
- `0x140036ea0`
- `0x14003d920`
- `0x1400472e0`
- `0x14004e050`
- `0x1400566b0`
- `0x14005a5c0`
- `0x14005b1f0`
- `0x14005edf0`
- `0x140063630`
- `0x140066ef0`
- `0x14007f2f0`
- `0x14007f480`
- `0x1400837ac`
- `0x140083b50`
- `0x1400873e0`
- `0x14008b44c`
- `0x14008b6d0`
- `0x1400b6320`
- `0x1400e6240`
- `0x1400e65c0`
- `0x14014460c`
- `0x14014c228`
- `0x140156f20`
- `0x140157dc0`
- `0x14015b500`
- `0x14015c100`
- `0x140163350`
- `0x140163cc0`
- `0x140164280`
- `0x140168a90`
- `0x140169af0`
- `0x140178f70`
- `0x140179270`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1400b6b0a`
- `ntoskrnl!ExQueueWorkItem` at `0x1400b6b0a`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400b6694`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400b6694`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b6b7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b6b7e`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6958`
- `ntoskrnl!ExAllocatePool2` at `0x1400b6958`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b6715`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b6a0c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b6715`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b6a0c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b66de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b66de`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400b6842`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400b6842`
- `HAL!KeStallExecutionProcessor` at `0x1400b6853`
- `HAL!KeStallExecutionProcessor` at `0x1400b6853`

## pseudocode

```c

```
