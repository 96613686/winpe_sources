# CmsReadCache::InvalidateCacheInformation(CmsTransactionContext *,_RANGE const *,uchar,uchar,uchar)

- ea: `0x1c00c5c44`
- end: `0x1c00c6682`
- name: `?InvalidateCacheInformation@CmsReadCache@@QEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@EEE@Z`
- size: `2622`
- prototype: `__int64 __usercall@<rax>(CmsReadCache *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, const struct _RANGE *@<r8>, unsigned __int8@<r9b>, unsigned __int8, unsigned __int8)`
- caller_count: `11`
- callee_count: `22`
- tags: ``

## callers

- `0x1c004bc94`
- `0x1c0053e1c`
- `0x1c00b2300`
- `0x1c00bd324`
- `0x1c00c3500`
- `0x1c00c43c0`
- `0x1c00c5b80`
- `0x1c00c781c`
- `0x1c00e3074`
- `0x1c00e3b24`
- `0x1c00e3fa0`

## callees

- `0x1c00059f4`
- `0x1c00224d0`
- `0x1c002313c`
- `0x1c002357c`
- `0x1c002981c`
- `0x1c0047d84`
- `0x1c0064274`
- `0x1c0068960`
- `0x1c00b3750`
- `0x1c00c42e0`
- `0x1c00c59f0`
- `0x1c00c5a50`
- `0x1c00c5c44`
- `0x1c00c67c0`
- `0x1c00c6830`
- `0x1c00c6944`
- `0x1c00c74e0`
- `0x1c00c86f8`
- `0x1c00c8b04`
- `0x1c00c8c74`
- `0x1c00c8cfc`
- `0x1c00d725c`

## import_xrefs

- `ntoskrnl!ExReleasePushLockEx` at `0x1c00c5dde`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00c5dde`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00c6179`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00c62f6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00c6179`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c00c62f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00c61a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00c6570`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00c61a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00c6570`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00c5d9d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c00c5d9d`

## pseudocode

```c

```
