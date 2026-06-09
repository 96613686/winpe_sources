# UxSslAcceptSecurityContextCallback

- ea: `0x140050ba0`
- end: `0x140050d70`
- name: `UxSslAcceptSecurityContextCallback`
- size: `464`
- prototype: `void __stdcall(SspiAsyncContext *Handle, PVOID CallbackData)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000a350`
- `0x140022610`
- `0x140050920`
- `0x140050ba0`
- `0x1401c3008`
- `0x1401c3f58`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050c49`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050c49`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140050c3d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140050c3d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140050c07`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140050c07`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140050bf2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140050bf2`
- `HAL!KeQueryPerformanceCounter` at `0x140050bc4`
- `HAL!KeQueryPerformanceCounter` at `0x140050bc4`
- `ksecdd!SspiGetAsyncCallStatus` at `0x140050bd7`
- `ksecdd!SspiGetAsyncCallStatus` at `0x140050bd7`

## pseudocode

```c

```
