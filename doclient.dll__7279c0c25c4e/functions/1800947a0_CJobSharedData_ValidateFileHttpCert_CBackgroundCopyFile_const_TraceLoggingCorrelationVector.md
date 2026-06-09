# CJobSharedData::ValidateFileHttpCert(CBackgroundCopyFile const &,TraceLoggingCorrelationVector *)

- ea: `0x1800947a0`
- end: `0x180094b1d`
- name: `?ValidateFileHttpCert@CJobSharedData@@QEAAJAEBVCBackgroundCopyFile@@PEAVTraceLoggingCorrelationVector@@@Z`
- size: `893`
- prototype: `__int64 __fastcall(CJobSharedData *__hidden this, const struct CBackgroundCopyFile *, struct TraceLoggingCorrelationVector *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180081e20`

## callees

- `0x180008450`
- `0x18000933c`
- `0x1800095a0`
- `0x18000a4e0`
- `0x180019010`
- `0x1800944a8`
- `0x180094720`
- `0x1800947a0`
- `0x1800c4078`
- `0x1800f82f0`
- `0x1800f8320`
- `0x180108e50`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800948f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094ac5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800948f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094ac5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180094950`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180094950`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800947df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800949c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800947df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800949c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800947f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800947fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180094a13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180094a1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800947f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800947fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180094a13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180094a1e`
- `CRYPT32!CertFreeCertificateContext` at `0x1800948cc`
- `CRYPT32!CertFreeCertificateContext` at `0x180094ab6`
- `CRYPT32!CertFreeCertificateContext` at `0x1800948cc`
- `CRYPT32!CertFreeCertificateContext` at `0x180094ab6`

## string_xrefs

- `0x180094b0b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x18009492f`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`

## pseudocode

```c

```
