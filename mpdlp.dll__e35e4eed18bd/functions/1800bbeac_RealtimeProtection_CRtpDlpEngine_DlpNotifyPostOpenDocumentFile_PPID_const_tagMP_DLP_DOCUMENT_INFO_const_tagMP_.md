# RealtimeProtection::CRtpDlpEngine::DlpNotifyPostOpenDocumentFile(PPID const &,tagMP_DLP_DOCUMENT_INFO * const,tagMP_DLP_POSTOP_STATUS * const)

- ea: `0x1800bbeac`
- end: `0x1800bc158`
- name: `?DlpNotifyPostOpenDocumentFile@CRtpDlpEngine@RealtimeProtection@@QEAAJAEBUPPID@@QEAUtagMP_DLP_DOCUMENT_INFO@@QEAUtagMP_DLP_POSTOP_STATUS@@@Z`
- size: `684`
- prototype: `int(RealtimeProtection::CRtpDlpEngine *__hidden this, const struct PPID *, struct tagMP_DLP_DOCUMENT_INFO *const, struct tagMP_DLP_POSTOP_STATUS *const)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180143450`

## callees

- `0x180050300`
- `0x180079034`
- `0x18007a5c4`
- `0x1800809d0`
- `0x180089510`
- `0x180096a40`
- `0x1800afcac`
- `0x1800ba1f4`
- `0x1800bbeac`
- `0x18010ce3c`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x1800bbf78`
- `KERNEL32!AcquireSRWLockShared` at `0x1800bbf78`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800bc0f0`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800bc0fd`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800bc0f0`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800bc0fd`
- `KERNEL32!DebugBreak` at `0x1800bbee2`
- `KERNEL32!DebugBreak` at `0x1800bbee2`

## string_xrefs

- `0x1800bbecc`: `MpDlp_BreakOnOpenDocumentOfficeHint`
- `0x1800bbf43`: `RealtimeProtection::CRtpDlpEngine::DlpNotifyPostOpenDocumentFile`
- `0x1800bc00a`: `RealtimeProtection::CRtpDlpEngine::DlpNotifyPostOpenDocumentFile`
- `0x1800bc057`: `RealtimeProtection::CRtpDlpEngine::DlpNotifyPostOpenDocumentFile`

## pseudocode

```c

```
