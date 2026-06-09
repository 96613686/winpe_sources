# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x18001f040`
- end: `0x18001f091`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `81`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001ebcc`
- `0x18001f040`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001f085`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001f085`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x18001f057`
- `KERNEL32!TryAcquireSRWLockExclusive` at `0x18001f057`

## pseudocode

```c

```
