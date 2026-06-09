# CSharedLock::HrCleanupCrashedProcess(ulong,eSharedLockSecurity,unsigned __int64,CSharedPage *,CSharedHeap const *,void *)

- ea: `0x180111fa0`
- end: `0x180112126`
- name: `?HrCleanupCrashedProcess@CSharedLock@@SAJKW4eSharedLockSecurity@@_KPEAVCSharedPage@@PEBVCSharedHeap@@PEAX@Z`
- size: `390`
- prototype: `static int __high(unsigned int, enum eSharedLockSecurity, unsigned __int64, struct CSharedPage *, const struct CSharedHeap *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180111f80`

## callees

- `0x180037cf4`
- `0x18003e690`
- `0x1801116c0`
- `0x180111a60`
- `0x180111fa0`
- `0x180113100`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1801120d6`
- `KERNEL32!CloseHandle` at `0x1801120d6`
- `KERNEL32!SetEvent` at `0x1801120c5`
- `KERNEL32!SetEvent` at `0x1801120c5`

## pseudocode

```c

```
