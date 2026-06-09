# ndisOpenAdapterLegacyProtocol(int *,int *,void * *,uint *,_NDIS_MEDIUM *,uint,void *,void *,_UNICODE_STRING *,uint,_STRING *,int *)

- ea: `0x1400bb750`
- end: `0x1400bc05d`
- name: `?ndisOpenAdapterLegacyProtocol@@YAXPEAH0PEAPEAXPEAIPEAW4_NDIS_MEDIUM@@IPEAX4PEAU_UNICODE_STRING@@IPEAU_STRING@@0@Z`
- size: `2317`
- prototype: `void __usercall(int *@<rcx>, int *@<rdx>, void **@<r8>, unsigned int *@<r9>, enum _NDIS_MEDIUM *, unsigned int, KIRQL NewIrql, void *, struct _UNICODE_STRING *, unsigned int, struct _STRING *, int *)`
- caller_count: `2`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x140171510`
- `0x14017b410`

## callees

- `0x140005840`
- `0x140005c70`
- `0x140009320`
- `0x140010d20`
- `0x1400110b0`
- `0x14001fa30`
- `0x1400400d0`
- `0x14004bc60`
- `0x140053280`
- `0x14005aef0`
- `0x14005eaa0`
- `0x14005f7e0`
- `0x140063390`
- `0x140068a00`
- `0x14006ca10`
- `0x140084b80`
- `0x140084d00`
- `0x140088a2c`
- `0x140088dd0`
- `0x14008c6d0`
- `0x140095884`
- `0x140095b08`
- `0x1400bb750`
- `0x1400eb460`
- `0x1400eb7c0`
- `0x14014b5ac`
- `0x1401531c8`
- `0x14015dec0`
- `0x14015ed60`
- `0x1401624a0`
- `0x1401630a0`
- `0x14016a2e0`
- `0x14016ac50`
- `0x14016b210`
- `0x14016f980`
- `0x1401709e0`
- `0x14017ef40`
- `0x14017f240`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1400bbf3a`
- `ntoskrnl!ExQueueWorkItem` at `0x1400bbf3a`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400bbac4`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400bbac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbfae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbfae`
- `ntoskrnl!ExAllocatePool2` at `0x1400bbd88`
- `ntoskrnl!ExAllocatePool2` at `0x1400bbd88`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bbb45`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bbe3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bbb45`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bbe3c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bbb0e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bbb0e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400bbc72`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400bbc72`
- `HAL!KeStallExecutionProcessor` at `0x1400bbc83`
- `HAL!KeStallExecutionProcessor` at `0x1400bbc83`

## pseudocode

```c

```
