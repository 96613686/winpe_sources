# USER_SESSION::DoCustomAuthorization(ushort const *,_FTP_ACCESS,FTP_SITE_CONFIG *,int *)

- ea: `0x18000fb34`
- end: `0x18000fdd0`
- name: `?DoCustomAuthorization@USER_SESSION@@AEAAJPEBGW4_FTP_ACCESS@@PEAVFTP_SITE_CONFIG@@PEAH@Z`
- size: `668`
- prototype: `__int64 __fastcall(USER_SESSION *__hidden this, const unsigned __int16 *, enum _FTP_ACCESS, struct FTP_SITE_CONFIG *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000e5cc`

## callees

- `0x18000fb34`
- `0x1800199d4`
- `0x180019b48`
- `0x18002c12c`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000fc72`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000fc72`
- `iisutil!PuDbgPrintError` at `0x18000fcc0`
- `iisutil!PuDbgPrintError` at `0x18000fdc5`
- `iisutil!PuDbgPrintError` at `0x18000fcc0`
- `iisutil!PuDbgPrintError` at `0x18000fdc5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000fd12`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000fd89`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000fd12`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000fd89`

## string_xrefs

- `0x18000fc95`: `Failed to call pFtpAuthorizationProvider->GetUserAccessPermission(). Exception details: %S\n`

## pseudocode

```c

```
