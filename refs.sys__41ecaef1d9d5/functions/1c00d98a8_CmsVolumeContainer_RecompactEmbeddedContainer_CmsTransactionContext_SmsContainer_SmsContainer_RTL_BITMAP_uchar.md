# CmsVolumeContainer::RecompactEmbeddedContainer(CmsTransactionContext *,SmsContainer *,SmsContainer *,_RTL_BITMAP *,uchar *,unsigned __int64,uchar *,unsigned __int64,uchar,__int64 *,_RANGE_TUPLE *,_RANGE_TUPLE *,unsigned __int64 *,CmsContainerRangeMap *,ushort *,SmsCompactionUndoChain * *)

- ea: `0x1c00d98a8`
- end: `0x1c00da1dd`
- name: `?RecompactEmbeddedContainer@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAUSmsContainer@@1PEAU_RTL_BITMAP@@PEAE_K34EPEA_JPEAU_RANGE_TUPLE@@6PEA_KPEAVCmsContainerRangeMap@@PEAGPEAPEAUSmsCompactionUndoChain@@@Z`
- size: `2357`
- prototype: `__int64 __usercall@<rax>(CmsVolumeContainer *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct SmsContainer *@<r8>, struct SmsContainer *@<r9>, struct _RTL_BITMAP *, unsigned __int8 *, unsigned __int64, unsigned __int8 *, unsigned __int64, char, __int64 *, struct _RANGE_TUPLE *, struct _RANGE_TUPLE *, unsigned __int64 *, struct CmsContainerRangeMap *, unsigned __int16 *, struct SmsCompactionUndoChain **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1c00d34d0`

## callees

- `0x1c0028ebc`
- `0x1c002a564`
- `0x1c005bfe8`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c00d7c10`
- `0x1c00d98a8`
- `0x1c00f5e6c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00d9a3d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00d9a3d`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d9c78`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d9c9e`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d9cc4`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d9c78`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d9c9e`
- `ntoskrnl!RtlInitializeBitMap` at `0x1c00d9cc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00da1ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00da1ab`
- `ntoskrnl!RtlSetBits` at `0x1c00da01b`
- `ntoskrnl!RtlSetBits` at `0x1c00da01b`
- `ntoskrnl!RtlClearBits` at `0x1c00d9eb0`
- `ntoskrnl!RtlClearBits` at `0x1c00d9ff1`
- `ntoskrnl!RtlClearBits` at `0x1c00d9eb0`
- `ntoskrnl!RtlClearBits` at `0x1c00d9ff1`
- `ntoskrnl!RtlNumberOfSetBitsInRange` at `0x1c00d9db2`
- `ntoskrnl!RtlNumberOfSetBitsInRange` at `0x1c00d9db2`

## pseudocode

```c

```
