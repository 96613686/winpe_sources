# NlChangeCachedPasswords(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x180053350`
- end: `0x1800535a8`
- name: `?NlChangeCachedPasswords@@YAXPEAU_UNICODE_STRING@@00@Z`
- size: `600`
- prototype: `void __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180033a34`

## callees

- `0x180003220`
- `0x180007278`
- `0x18000e270`
- `0x18000ed34`
- `0x1800160a0`
- `0x180053350`
- `0x180089a30`
- `0x180089ab4`
- `0x18008a010`

## import_xrefs

- `LSASRV!LsaICallPackage` at `0x18005353f`
- `LSASRV!LsaICallPackage` at `0x18005353f`
- `LSASRV!LsaIFreeReturnBuffer` at `0x18005356a`
- `LSASRV!LsaIFreeReturnBuffer` at `0x18005356a`
- `ntdll!RtlInitUnicodeString` at `0x1800534a5`
- `ntdll!RtlInitUnicodeString` at `0x1800534ca`
- `ntdll!RtlInitUnicodeString` at `0x1800534ef`
- `ntdll!RtlInitUnicodeString` at `0x180053519`
- `ntdll!RtlInitUnicodeString` at `0x1800534a5`
- `ntdll!RtlInitUnicodeString` at `0x1800534ca`
- `ntdll!RtlInitUnicodeString` at `0x1800534ef`
- `ntdll!RtlInitUnicodeString` at `0x180053519`

## string_xrefs

- `0x180053460`: `NlChangeCachedPasswords failed with allocation failure.\n`
- `0x180053502`: `NlChangeCachedPasswords changing cached passwords for %wZ\%wZ\n`
- `0x18005354d`: `NlChangeCachedPasswords: failed to update logon sessions with status 0x%08X, substatus 0x%08X\n`

## pseudocode

```c

```
