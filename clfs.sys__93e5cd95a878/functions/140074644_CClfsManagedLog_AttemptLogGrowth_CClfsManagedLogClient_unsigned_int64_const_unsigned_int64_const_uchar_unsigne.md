# CClfsManagedLog::AttemptLogGrowth(CClfsManagedLogClient *,unsigned __int64 const &,unsigned __int64 const &,uchar,unsigned __int64 &)

- ea: `0x140074644`
- end: `0x14007474b`
- name: `?AttemptLogGrowth@CClfsManagedLog@@AEAAJPEAVCClfsManagedLogClient@@AEB_K1EAEA_K@Z`
- size: `263`
- prototype: `__int64 __usercall@<rax>(CClfsManagedLog *__hidden this@<rcx>, struct CClfsManagedLogClient *@<rdx>, const unsigned __int64 *@<r8>, const unsigned __int64 *@<r9>, char, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140050d5c`
- `0x1400510c0`
- `0x140074410`

## callees

- `0x140032294`
- `0x140074644`
- `0x140074754`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140074675`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140074675`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007472b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007472b`

## pseudocode

```c

```
