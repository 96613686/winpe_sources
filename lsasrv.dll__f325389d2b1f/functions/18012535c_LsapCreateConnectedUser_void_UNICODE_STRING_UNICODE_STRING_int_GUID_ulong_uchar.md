# LsapCreateConnectedUser(void *,_UNICODE_STRING *,_UNICODE_STRING *,int,_GUID *,ulong,uchar *)

- ea: `0x18012535c`
- end: `0x1801257de`
- name: `?LsapCreateConnectedUser@@YAJPEAXPEAU_UNICODE_STRING@@1HPEAU_GUID@@KPEAE@Z`
- size: `1154`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, struct _UNICODE_STRING *@<rdx>, struct _UNICODE_STRING *@<r8>, int@<r9d>, struct _GUID *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting`

## callers

- `0x18012a780`

## callees

- `0x1800040d0`
- `0x180009330`
- `0x18000c300`
- `0x180011278`
- `0x18005fecc`
- `0x18006064c`
- `0x180060cb0`
- `0x180074aa8`
- `0x18007fbd0`
- `0x1800b86d0`
- `0x1800bd6e0`
- `0x180123548`
- `0x180124e68`
- `0x18012535c`
- `0x1801257e4`
- `0x180127bf4`
- `0x18012cd8c`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012579b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012579b`
- `ntdll!RtlAcquireResourceExclusive` at `0x1801254f8`
- `ntdll!RtlAcquireResourceExclusive` at `0x1801254f8`
- `ntdll!RtlReleaseResource` at `0x180125537`
- `ntdll!RtlReleaseResource` at `0x180125537`
- `ntdll!RtlGetLastNtStatus` at `0x1801256c4`
- `ntdll!RtlGetLastNtStatus` at `0x1801256c4`
- `USERENV!UnloadUserProfile` at `0x18012570b`
- `USERENV!UnloadUserProfile` at `0x18012570b`
- `USERENV!LoadUserProfileW` at `0x1801256b4`
- `USERENV!LoadUserProfileW` at `0x1801256b4`
- `SspiCli!SspiLocalFree` at `0x180125740`
- `SspiCli!SspiLocalFree` at `0x180125740`

## string_xrefs

- `0x180125549`: `LsapCreateConnectedAccountInSam`
- `0x180125774`: `LsapSamExtDeleteUser`
- `0x1801253a0`: `LsapCreateConnectedUser`
- `0x180125410`: `LsapCreateConnectedUser`
- `0x1801257aa`: `LsapCreateConnectedUser`

## pseudocode

```c

```
