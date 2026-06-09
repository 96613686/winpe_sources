# RealtimeProtection::CRtpDlpEngine::CheckEnforcementForEgressOperation(DlpActionType,RealtimeProtection::MpDlpOperationOrigin,PPID const &,ulong,wchar_t const *,ulong,wchar_t const *,wchar_t const *,bool,tagDlp_Enforcement_Decision *)

- ea: `0x180076f64`
- end: `0x180079032`
- name: `?CheckEnforcementForEgressOperation@CRtpDlpEngine@RealtimeProtection@@QEAAJW4DlpActionType@@W4MpDlpOperationOrigin@2@AEBUPPID@@KPEB_WK33_NPEAW4tagDlp_Enforcement_Decision@@@Z`
- size: `8398`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `62`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18018c388`

## callees

- `0x180018848`
- `0x1800249f0`
- `0x180024ac0`
- `0x180028d80`
- `0x180029590`
- `0x18002b050`
- `0x18002c150`
- `0x180033520`
- `0x180034420`
- `0x180037afc`
- `0x180038450`
- `0x180042f34`
- `0x180042f68`
- `0x1800442d0`
- `0x180048e20`
- `0x180049b34`
- `0x18004b3bc`
- `0x180059508`
- `0x180059954`
- `0x18006af4c`
- `0x18006b998`
- `0x180076f28`
- `0x180076f64`
- `0x180079034`
- `0x1800792bc`
- `0x180079348`
- `0x180079424`
- `0x180079594`
- `0x1800799c8`
- `0x180079b8c`
- `0x180079dc0`
- `0x18007a698`
- `0x18007f5fc`
- `0x180080030`
- `0x1800809d0`
- `0x1800857d0`
- `0x180089510`
- `0x18009351c`
- `0x18009f730`
- `0x1800a8c30`
- `0x180105f50`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18010d20c`
- `0x180128710`
- `0x1801405f4`
- `0x1801459c8`
- `0x18016a698`
- `0x1801840a8`
- `0x180184244`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x180077167`
- `KERNEL32!AcquireSRWLockShared` at `0x180077167`
- `KERNEL32!ReleaseSRWLockShared` at `0x180077225`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800772d3`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007738c`
- `KERNEL32!ReleaseSRWLockShared` at `0x180077491`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800774e8`
- `KERNEL32!ReleaseSRWLockShared` at `0x180077731`
- `KERNEL32!ReleaseSRWLockShared` at `0x180077cb1`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007805e`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078119`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078269`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078463`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078531`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800789e9`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078dd6`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078e95`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078f40`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078f4f`
- `KERNEL32!ReleaseSRWLockShared` at `0x180077225`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800772d3`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007738c`
- `KERNEL32!ReleaseSRWLockShared` at `0x180077491`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800774e8`
- `KERNEL32!ReleaseSRWLockShared` at `0x180077731`
- `KERNEL32!ReleaseSRWLockShared` at `0x180077cb1`
- `KERNEL32!ReleaseSRWLockShared` at `0x18007805e`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078119`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078269`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078463`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078531`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800789e9`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078dd6`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078e95`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078f40`
- `KERNEL32!ReleaseSRWLockShared` at `0x180078f4f`
- `ADVAPI32!RevertToSelf` at `0x1800776c5`
- `ADVAPI32!RevertToSelf` at `0x180077765`
- `ADVAPI32!RevertToSelf` at `0x1800776c5`
- `ADVAPI32!RevertToSelf` at `0x180077765`

## string_xrefs

- `0x180077d67`: `DLP:::CheckEnforcementForEgressOperation(%d): Determine operation enforcement complete. Src %ls, Dest %ls, Enforce %d, decision %ls, reason %ls`
- `0x180077286`: `DLP::CheckEnforcementForEgressOperation(%d): Error while converting SrcPath(DOS) to FilterPath. Err= 0x%x, Src= %ls`
- `0x18007732c`: `DLP::CheckEnforcementForEgressOperation(%d): Error while converting DestPath(DOS) to FilterPath. Err= 0x%x, Dest= %ls`

## pseudocode

```c

```
