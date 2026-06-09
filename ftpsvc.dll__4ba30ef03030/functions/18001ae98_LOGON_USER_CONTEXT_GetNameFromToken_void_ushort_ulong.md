# LOGON_USER_CONTEXT::GetNameFromToken(void *,ushort *,ulong *)

- ea: `0x18001ae98`
- end: `0x18001af26`
- name: `?GetNameFromToken@LOGON_USER_CONTEXT@@AEAAJPEAXPEAGPEAK@Z`
- size: `142`
- prototype: `__int64 __fastcall(LOGON_USER_CONTEXT *this, void *, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18001b3ac`
- `0x18001b90c`

## callees

- `0x18001ae98`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001aeba`
- `KERNEL32!GetLastError` at `0x18001aef9`
- `KERNEL32!GetLastError` at `0x18001aeba`
- `KERNEL32!GetLastError` at `0x18001aef9`
- `ADVAPI32!RevertToSelf` at `0x18001af0e`
- `ADVAPI32!RevertToSelf` at `0x18001af0e`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18001aeb0`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18001aeb0`
- `Secur32!GetUserNameExW` at `0x18001aedc`
- `Secur32!GetUserNameExW` at `0x18001aeef`
- `Secur32!GetUserNameExW` at `0x18001aedc`
- `Secur32!GetUserNameExW` at `0x18001aeef`

## pseudocode

```c

```
