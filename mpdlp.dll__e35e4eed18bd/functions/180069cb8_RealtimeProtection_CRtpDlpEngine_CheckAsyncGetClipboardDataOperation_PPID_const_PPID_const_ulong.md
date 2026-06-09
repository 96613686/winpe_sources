# RealtimeProtection::CRtpDlpEngine::CheckAsyncGetClipboardDataOperation(PPID const &,PPID const &,ulong)

- ea: `0x180069cb8`
- end: `0x18006a37c`
- name: `?CheckAsyncGetClipboardDataOperation@CRtpDlpEngine@RealtimeProtection@@QEAAJAEBUPPID@@0K@Z`
- size: `1732`
- prototype: `__int64 __fastcall(RealtimeProtection::CRtpDlpEngine *this, const struct PPID *, FILETIME *, unsigned int)`
- caller_count: `2`
- callee_count: `32`
- tags: ``

## callers

- `0x1800688fc`
- `0x180143f30`

## callees

- `0x18001dc40`
- `0x18001de1c`
- `0x18001f090`
- `0x180029590`
- `0x18002b050`
- `0x180034420`
- `0x180038450`
- `0x1800399c0`
- `0x18003df30`
- `0x18003e488`
- `0x18003ffd0`
- `0x180046d10`
- `0x180069cb8`
- `0x180074f60`
- `0x180075448`
- `0x180076f28`
- `0x180079348`
- `0x180079dc0`
- `0x1800809d0`
- `0x18008ac70`
- `0x1800a1b90`
- `0x1800afbc0`
- `0x1800bb4ec`
- `0x1800bc560`
- `0x180101348`
- `0x1801018c4`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18014d290`
- `0x18014df1c`
- `0x18019b6d0`
- `0x1801d9bac`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x180069f8d`
- `KERNEL32!ReleaseSRWLockShared` at `0x180069fa8`
- `KERNEL32!ReleaseSRWLockShared` at `0x18006a041`
- `KERNEL32!ReleaseSRWLockShared` at `0x18006a128`
- `KERNEL32!ReleaseSRWLockShared` at `0x180069f8d`
- `KERNEL32!ReleaseSRWLockShared` at `0x180069fa8`
- `KERNEL32!ReleaseSRWLockShared` at `0x18006a041`
- `KERNEL32!ReleaseSRWLockShared` at `0x18006a128`
- `KERNEL32!CloseHandle` at `0x180069e48`
- `KERNEL32!CloseHandle` at `0x180069e97`
- `KERNEL32!CloseHandle` at `0x180069e48`
- `KERNEL32!CloseHandle` at `0x180069e97`

## string_xrefs

- `0x18006a349`: `CheckAsyncGetClipboardDataOperation: CheckAccessForOperation returned with decision = %ls, reason=%ls, owner PID = %lu, reader PID = %lu, reader image name = %ls, Seq num %lu.`

## pseudocode

```c

```
