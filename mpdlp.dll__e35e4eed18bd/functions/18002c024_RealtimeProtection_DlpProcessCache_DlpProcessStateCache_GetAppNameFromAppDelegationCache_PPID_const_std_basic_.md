# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetAppNameFromAppDelegationCache(PPID const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18002c024`
- end: `0x18002c14c`
- name: `?GetAppNameFromAppDelegationCache@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEBAJAEBUPPID@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002bf88`

## callees

- `0x18002c024`
- `0x18002c150`
- `0x180107874`
- `0x18010cb40`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x18002c05c`
- `KERNEL32!AcquireSRWLockShared` at `0x18002c05c`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002c0b1`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002c0f7`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002c0b1`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002c0f7`
- `KERNEL32!CompareFileTime` at `0x18002c120`
- `KERNEL32!CompareFileTime` at `0x18002c120`

## pseudocode

```c

```
