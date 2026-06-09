# UxSslAcceptSecurityContextCallback

- ea: `0x1c00c8480`
- end: `0x1c00c8550`
- name: `UxSslAcceptSecurityContextCallback`
- size: `208`
- prototype: `void __stdcall(SspiAsyncContext *Handle, PVOID CallbackData)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1c0001ae0`
- `0x1c000eb40`
- `0x1c001a8ac`
- `0x1c00c8480`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00c850c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00c850c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c84da`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00c84da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00c8518`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00c8518`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00c84c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00c84c2`
- `HAL!KeQueryPerformanceCounter` at `0x1c00c8497`
- `HAL!KeQueryPerformanceCounter` at `0x1c00c8497`
- `ksecdd!SspiGetAsyncCallStatus` at `0x1c00c84aa`
- `ksecdd!SspiGetAsyncCallStatus` at `0x1c00c84aa`

## pseudocode

```c

```
