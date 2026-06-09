# LsapIdProvHostSaveUserInfo(void *,ushort *,_LSA_IDENTITY_INFO_CLASS,void *,ulong)

- ea: `0x180063030`
- end: `0x1800638e5`
- name: `?LsapIdProvHostSaveUserInfo@@YAJPEAXPEAGW4_LSA_IDENTITY_INFO_CLASS@@0K@Z`
- size: `2229`
- prototype: `int __high(void *, unsigned __int16 *, enum _LSA_IDENTITY_INFO_CLASS, void *, unsigned int)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c300`
- `0x18000f808`
- `0x180011278`
- `0x18005e7ec`
- `0x18005fa30`
- `0x18005fecc`
- `0x18006064c`
- `0x180061c7c`
- `0x180063030`
- `0x180063c24`
- `0x18006442c`
- `0x1800781fc`
- `0x180078a74`
- `0x18007c560`
- `0x18007fbd0`
- `0x1800924a8`
- `0x1800b1fc8`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bbbfc`
- `0x1800c69bc`
- `0x1800c7e28`
- `0x180129580`
- `0x18012c85c`
- `0x18012c97c`
- `0x18012ca8c`
- `0x18012cc3c`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18006323f`
- `ntdll!RtlReleaseResource` at `0x18006323f`
- `ntdll!RtlAcquireResourceShared` at `0x180063119`
- `ntdll!RtlAcquireResourceShared` at `0x180063119`
- `ntdll!RtlInitUnicodeString` at `0x180063143`
- `ntdll!RtlInitUnicodeString` at `0x1800635ad`
- `ntdll!RtlInitUnicodeString` at `0x180063143`
- `ntdll!RtlInitUnicodeString` at `0x1800635ad`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_ULONG_ARRAY` at `0x180063269`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_ULONG_ARRAY` at `0x1800633e2`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_ULONG_ARRAY` at `0x180063269`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFree_SAMPR_ULONG_ARRAY` at `0x1800633e2`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrLookupNamesInDomain2` at `0x1800631b0`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrLookupNamesInDomain2` at `0x1800631b0`

## string_xrefs

- `0x1800636c5`: `LsapSamExtRidToSid`
- `0x1800637e8`: `LsapSetCredentialComplexity`
- `0x180063738`: `LsapSaveUserInternetSid`
- `0x18006367e`: `LsapUpdateIdpLogonStatistics`

## pseudocode

```c

```
