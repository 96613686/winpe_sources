# RealtimeProtection::CRtpDlpEngine::CheckAccessForTargetProcess(wchar_t const *,wchar_t const *,PPID const &,ulong,ulong,uchar *,MpDlpResultAccessDecision *,MpDlpResultAccessReason *)

- ea: `0x1801927b4`
- end: `0x1801933c8`
- name: `?CheckAccessForTargetProcess@CRtpDlpEngine@RealtimeProtection@@QEAAJPEB_W0AEBUPPID@@KKPEAEPEAW4MpDlpResultAccessDecision@@PEAW4MpDlpResultAccessReason@@@Z`
- size: `3092`
- prototype: `int(RealtimeProtection::CRtpDlpEngine *__hidden this, const wchar_t *, const wchar_t *, const struct PPID *, unsigned int, unsigned int, unsigned __int8 *, enum MpDlpResultAccessDecision *, enum MpDlpResultAccessReason *)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation`

## callers

- `0x18018cc50`

## callees

- `0x18001a444`
- `0x1800249f0`
- `0x180027a90`
- `0x180028d80`
- `0x180029590`
- `0x180034420`
- `0x180038450`
- `0x180049b34`
- `0x18006af4c`
- `0x18006b998`
- `0x180076f28`
- `0x180079348`
- `0x180079b8c`
- `0x180080030`
- `0x1800809d0`
- `0x1800857d0`
- `0x18008ac70`
- `0x1800947f0`
- `0x18009d58c`
- `0x1800a2940`
- `0x1800a4c30`
- `0x1800b7ef0`
- `0x180105f50`
- `0x18010674c`
- `0x18010cb40`
- `0x18010ce3c`
- `0x1801405f4`
- `0x1801927b4`
- `0x1801a365c`
- `0x1801a47e4`
- `0x1801d73bc`
- `0x18023a310`

## import_xrefs

- `KERNEL32!GetDriveTypeW` at `0x1801929d5`
- `KERNEL32!GetDriveTypeW` at `0x1801929d5`
- `KERNEL32!ReleaseSRWLockShared` at `0x180192913`
- `KERNEL32!ReleaseSRWLockShared` at `0x180192c26`
- `KERNEL32!ReleaseSRWLockShared` at `0x180192d7d`
- `KERNEL32!ReleaseSRWLockShared` at `0x180192f93`
- `KERNEL32!ReleaseSRWLockShared` at `0x180193357`
- `KERNEL32!ReleaseSRWLockShared` at `0x180192913`
- `KERNEL32!ReleaseSRWLockShared` at `0x180192c26`
- `KERNEL32!ReleaseSRWLockShared` at `0x180192d7d`
- `KERNEL32!ReleaseSRWLockShared` at `0x180192f93`
- `KERNEL32!ReleaseSRWLockShared` at `0x180193357`
- `ADVAPI32!RevertToSelf` at `0x180192ad6`
- `ADVAPI32!RevertToSelf` at `0x180192ad6`

## pseudocode

```c

```
