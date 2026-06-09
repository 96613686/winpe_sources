# LsapUpdateFormatsForLogon(_LSAP_LOGON_SESSION *,ushort *,ushort *,EXTENDED_NAME_FORMAT *,ulong,ulong,_LSAP_DS_NAME_MAP * *)

- ea: `0x18007f3b0`
- end: `0x18007f95b`
- name: `?LsapUpdateFormatsForLogon@@YAKPEAU_LSAP_LOGON_SESSION@@PEAG1PEAW4EXTENDED_NAME_FORMAT@@KKPEAPEAU_LSAP_DS_NAME_MAP@@@Z`
- size: `1451`
- prototype: `unsigned int __fastcall(struct _LSAP_LOGON_SESSION *, unsigned __int16 *, unsigned __int16 *, enum EXTENDED_NAME_FORMAT *, unsigned int, unsigned int, struct _LSAP_DS_NAME_MAP **)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x18007ef50`
- `0x1800cd01c`

## callees

- `0x180003afc`
- `0x180007268`
- `0x180009330`
- `0x18007f3b0`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bb180`
- `0x1800bd6e0`
- `0x1800ce5f0`
- `0x1800cf0dc`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18007f85c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18007f85c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007f7e7`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18007f7e7`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18007f4ec`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18007f4ec`
- `ntdll!RtlGetLastWin32Error` at `0x18007f47e`
- `ntdll!RtlGetLastWin32Error` at `0x18007f47e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007f6d6`
- `ntdll!RtlAcquireResourceExclusive` at `0x18007f6d6`
- `ntdll!RtlReleaseResource` at `0x18007f542`
- `ntdll!RtlReleaseResource` at `0x18007f542`
- `ntdll!RtlNtStatusToDosError` at `0x18007f525`
- `ntdll!RtlNtStatusToDosError` at `0x18007f525`
- `ntdll!RtlInitUnicodeString` at `0x18007f73c`
- `ntdll!RtlInitUnicodeString` at `0x18007f8a1`
- `ntdll!RtlInitUnicodeString` at `0x18007f73c`
- `ntdll!RtlInitUnicodeString` at `0x18007f8a1`
- `ext-ms-win-secur32-translatename-l1-1-0!SecpTranslateNameEx` at `0x18007f468`
- `ext-ms-win-secur32-translatename-l1-1-0!SecpTranslateNameEx` at `0x18007f468`
- `ext-ms-win-secur32-translatename-l1-1-0!SecpFreeMemory` at `0x18007f5d6`
- `ext-ms-win-secur32-translatename-l1-1-0!SecpFreeMemory` at `0x18007f5ed`
- `ext-ms-win-secur32-translatename-l1-1-0!SecpFreeMemory` at `0x18007f5d6`
- `ext-ms-win-secur32-translatename-l1-1-0!SecpFreeMemory` at `0x18007f5ed`

## pseudocode

```c

```
