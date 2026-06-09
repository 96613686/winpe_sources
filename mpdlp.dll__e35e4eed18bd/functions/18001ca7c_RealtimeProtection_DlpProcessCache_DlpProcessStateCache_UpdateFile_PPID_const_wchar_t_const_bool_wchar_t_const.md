# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::UpdateFile(PPID const &,wchar_t const *,bool,wchar_t const *,std::optional<RealtimeProtection::FileUniqueId> const &,ulong,DlpAction *,RealtimeProtection::MpDlpPolicyTraceInfo const &,DlpAppGroupInfo const &,bool,ulong,uchar *,bool)

- ea: `0x18001ca7c`
- end: `0x18001cd7b`
- name: `?UpdateFile@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJAEBUPPID@@PEB_W_N1AEBV?$optional@VFileUniqueId@RealtimeProtection@@@std@@KPEAUDlpAction@@AEBUMpDlpPolicyTraceInfo@3@AEBUDlpAppGroupInfo@@2KPEAE2@Z`
- size: `767`
- prototype: `__int64 __usercall@<rax>(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *this@<rcx>, struct PPID *@<rdx>, __int64, __int64, int, __int64, __int64, __int64, char, int, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18001bc88`

## callees

- `0x18001bad0`
- `0x18001ca7c`
- `0x18001cd7c`
- `0x18002ba50`
- `0x1800809d0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18001cafb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001cafb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cbd7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cd0b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cd18`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cbd7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cd0b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001cd18`

## pseudocode

```c

```
