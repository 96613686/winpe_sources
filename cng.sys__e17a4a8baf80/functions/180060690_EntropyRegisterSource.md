# EntropyRegisterSource

- ea: `0x180060690`
- end: `0x180060940`
- name: `EntropyRegisterSource`
- size: `688`
- prototype: `NTSTATUS __stdcall(ENTROPY_SOURCE_HANDLE *phEntropySource, ENTROPY_SOURCE_TYPE entropySourceType, PCWSTR entropySourceName)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800610f4`
- `0x18006174c`
- `0x180067770`
- `0x180067c78`
- `0x1800a8de0`

## callees

- `0x18001155c`
- `0x180025fb0`
- `0x18002eb64`
- `0x1800402e0`
- `0x180060690`
- `0x180060cc4`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1800608bb`
- `ntoskrnl!KeReleaseMutex` at `0x1800608bb`
- `ntoskrnl!SkReleasePushLockExclusive` at `0x1800608ab`
- `ntoskrnl!SkReleasePushLockExclusive` at `0x1800608ab`
- `ntoskrnl!KeWaitForSingleObject` at `0x18006085e`
- `ntoskrnl!KeWaitForSingleObject` at `0x18006085e`
- `ntoskrnl!SkAcquirePushLockExclusive` at `0x180060843`
- `ntoskrnl!SkAcquirePushLockExclusive` at `0x180060843`
- `ntoskrnl!SkInitializePushLock` at `0x1800606e7`
- `ntoskrnl!SkInitializePushLock` at `0x180060813`
- `ntoskrnl!SkInitializePushLock` at `0x1800606e7`
- `ntoskrnl!SkInitializePushLock` at `0x180060813`
- `ntoskrnl!KeInitializeMutex` at `0x1800606f7`
- `ntoskrnl!KeInitializeMutex` at `0x1800606f7`
- `ntoskrnl!KeInitializeSpinLock` at `0x180060821`
- `ntoskrnl!KeInitializeSpinLock` at `0x180060821`

## string_xrefs

- `0x180060919`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\entropyapi.c`

## pseudocode

```c

```
