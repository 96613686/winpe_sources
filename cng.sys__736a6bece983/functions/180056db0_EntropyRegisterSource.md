# EntropyRegisterSource

- ea: `0x180056db0`
- end: `0x180057060`
- name: `EntropyRegisterSource`
- size: `688`
- prototype: `NTSTATUS __stdcall(ENTROPY_SOURCE_HANDLE *phEntropySource, ENTROPY_SOURCE_TYPE entropySourceType, PCWSTR entropySourceName)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180057814`
- `0x180057e6c`
- `0x18005de90`
- `0x18005e398`
- `0x1800a3e70`

## callees

- `0x18000743c`
- `0x180018f30`
- `0x180021af4`
- `0x180036d70`
- `0x180056db0`
- `0x1800573e4`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180056fdb`
- `ntoskrnl!KeReleaseMutex` at `0x180056fdb`
- `ntoskrnl!SkReleasePushLockExclusive` at `0x180056fcb`
- `ntoskrnl!SkReleasePushLockExclusive` at `0x180056fcb`
- `ntoskrnl!KeWaitForSingleObject` at `0x180056f7e`
- `ntoskrnl!KeWaitForSingleObject` at `0x180056f7e`
- `ntoskrnl!SkAcquirePushLockExclusive` at `0x180056f63`
- `ntoskrnl!SkAcquirePushLockExclusive` at `0x180056f63`
- `ntoskrnl!SkInitializePushLock` at `0x180056e07`
- `ntoskrnl!SkInitializePushLock` at `0x180056f33`
- `ntoskrnl!SkInitializePushLock` at `0x180056e07`
- `ntoskrnl!SkInitializePushLock` at `0x180056f33`
- `ntoskrnl!KeInitializeMutex` at `0x180056e17`
- `ntoskrnl!KeInitializeMutex` at `0x180056e17`
- `ntoskrnl!KeInitializeSpinLock` at `0x180056f41`
- `ntoskrnl!KeInitializeSpinLock` at `0x180056f41`

## string_xrefs

- `0x180057039`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\entropyapi.c`

## pseudocode

```c

```
