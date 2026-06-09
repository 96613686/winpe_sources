# EntropyRegisterSource

- ea: `0x1800564c0`
- end: `0x180056770`
- name: `EntropyRegisterSource`
- size: `688`
- prototype: `NTSTATUS __stdcall(ENTROPY_SOURCE_HANDLE *phEntropySource, ENTROPY_SOURCE_TYPE entropySourceType, PCWSTR entropySourceName)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180056f24`
- `0x18005757c`
- `0x18005d5a0`
- `0x18005daa8`
- `0x1800a2040`

## callees

- `0x18000743c`
- `0x18001be80`
- `0x180024a34`
- `0x180036270`
- `0x1800564c0`
- `0x180056af4`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1800566eb`
- `ntoskrnl!KeReleaseMutex` at `0x1800566eb`
- `ntoskrnl!SkReleasePushLockExclusive` at `0x1800566db`
- `ntoskrnl!SkReleasePushLockExclusive` at `0x1800566db`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005668e`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005668e`
- `ntoskrnl!SkAcquirePushLockExclusive` at `0x180056673`
- `ntoskrnl!SkAcquirePushLockExclusive` at `0x180056673`
- `ntoskrnl!SkInitializePushLock` at `0x180056517`
- `ntoskrnl!SkInitializePushLock` at `0x180056643`
- `ntoskrnl!SkInitializePushLock` at `0x180056517`
- `ntoskrnl!SkInitializePushLock` at `0x180056643`
- `ntoskrnl!KeInitializeMutex` at `0x180056527`
- `ntoskrnl!KeInitializeMutex` at `0x180056527`
- `ntoskrnl!KeInitializeSpinLock` at `0x180056651`
- `ntoskrnl!KeInitializeSpinLock` at `0x180056651`

## string_xrefs

- `0x180056749`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\entropyapi.c`

## pseudocode

```c

```
