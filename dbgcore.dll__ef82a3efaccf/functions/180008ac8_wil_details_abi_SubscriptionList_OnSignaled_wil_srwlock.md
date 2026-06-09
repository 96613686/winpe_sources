# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180008ac8`
- end: `0x180008b8e`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `198`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003450`
- `0x180003480`
- `0x180003530`
- `0x18000b7e0`

## callees

- `0x180008ac8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008ae7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008ae7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008b01`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008b01`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b76`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b17`

## pseudocode

```c

```
