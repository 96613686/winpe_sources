# NlChangeCachedPasswords(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x180056cec`
- end: `0x180056f69`
- name: `?NlChangeCachedPasswords@@YAXPEAU_UNICODE_STRING@@00@Z`
- size: `637`
- prototype: `void __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180035924`

## callees

- `0x180003340`
- `0x180007518`
- `0x18000e910`
- `0x18000f3e4`
- `0x180016aa4`
- `0x180056cec`
- `0x180090180`
- `0x180090204`
- `0x180091010`

## import_xrefs

- `LSASRV!LsaICallPackage` at `0x180056ef3`
- `LSASRV!LsaICallPackage` at `0x180056ef3`
- `LSASRV!LsaIFreeReturnBuffer` at `0x180056f24`
- `LSASRV!LsaIFreeReturnBuffer` at `0x180056f24`
- `ntdll!RtlInitUnicodeString` at `0x180056e41`
- `ntdll!RtlInitUnicodeString` at `0x180056e6c`
- `ntdll!RtlInitUnicodeString` at `0x180056e97`
- `ntdll!RtlInitUnicodeString` at `0x180056ec7`
- `ntdll!RtlInitUnicodeString` at `0x180056e41`
- `ntdll!RtlInitUnicodeString` at `0x180056e6c`
- `ntdll!RtlInitUnicodeString` at `0x180056e97`
- `ntdll!RtlInitUnicodeString` at `0x180056ec7`

## string_xrefs

- `0x180056dfc`: `NlChangeCachedPasswords failed with allocation failure.\n`
- `0x180056eb0`: `NlChangeCachedPasswords changing cached passwords for %wZ\%wZ\n`
- `0x180056f07`: `NlChangeCachedPasswords: failed to update logon sessions with status 0x%08X, substatus 0x%08X\n`

## pseudocode

```c

```
