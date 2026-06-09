# RealtimeProtection::CRtpDlpEngine::DlpNotifyPreOpenDocumentFile(PPID const &,tagMP_DLP_DOCUMENT_INFO * const)

- ea: `0x18007a024`
- end: `0x18007a27b`
- name: `?DlpNotifyPreOpenDocumentFile@CRtpDlpEngine@RealtimeProtection@@QEAAJAEBUPPID@@QEAUtagMP_DLP_DOCUMENT_INFO@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(RealtimeProtection::CRtpDlpEngine *__hidden this, const struct PPID *, struct tagMP_DLP_DOCUMENT_INFO *const)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800b18a0`

## callees

- `0x180050300`
- `0x180079034`
- `0x18007a024`
- `0x18007a5c4`
- `0x1800809d0`
- `0x180089510`
- `0x1800afcac`
- `0x1800ba1f4`
- `0x18010ce3c`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x18007a0a0`
- `KERNEL32!AcquireSRWLockShared` at `0x18007a0a0`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007a214`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007a222`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007a214`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007a222`
- `KERNEL32!DebugBreak` at `0x18007a057`
- `KERNEL32!DebugBreak` at `0x18007a057`

## string_xrefs

- `0x18007a041`: `MpDlp_BreakOnOpenDocumentOfficeHint`
- `0x18007a181`: `RealtimeProtection::CRtpDlpEngine::DlpNotifyPreOpenDocumentFile`

## pseudocode

```c

```
