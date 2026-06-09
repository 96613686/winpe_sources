# UxSslAcceptSecurityContextCallback

- ea: `0x140050b80`
- end: `0x140050d50`
- name: `UxSslAcceptSecurityContextCallback`
- size: `464`
- prototype: `void __stdcall(SspiAsyncContext *Handle, PVOID CallbackData)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000a350`
- `0x140022610`
- `0x140050900`
- `0x140050b80`
- `0x1401c3008`
- `0x1401c3f58`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050c29`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050c29`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140050c1d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140050c1d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140050be7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140050be7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140050bd2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140050bd2`
- `HAL!KeQueryPerformanceCounter` at `0x140050ba4`
- `HAL!KeQueryPerformanceCounter` at `0x140050ba4`
- `ksecdd!SspiGetAsyncCallStatus` at `0x140050bb7`
- `ksecdd!SspiGetAsyncCallStatus` at `0x140050bb7`

## pseudocode

```c

```
