# KerbCheckCredMgrForGivenTarget(_KERB_LOGON_SESSION *,_KERB_CREDENTIAL *,_UNICODE_STRING *,_KERB_INTERNAL_NAME *,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_KERB_CREDMAN_CRED * *,uchar * *,ulong *)

- ea: `0x180062d28`
- end: `0x180063890`
- name: `?KerbCheckCredMgrForGivenTarget@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_KERB_CREDENTIAL@@PEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@K22PEAPEAU_KERB_CREDMAN_CRED@@PEAPEAEPEAK@Z`
- size: `2920`
- prototype: `int(struct _KERB_LOGON_SESSION *, struct _KERB_CREDENTIAL *, struct _UNICODE_STRING *, struct _KERB_INTERNAL_NAME *, unsigned int, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _KERB_CREDMAN_CRED **, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021574`
- `0x1800a56e0`
- `0x1800cc8a8`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x180006f04`
- `0x180007e80`
- `0x18001018c`
- `0x1800107f8`
- `0x1800163a0`
- `0x18001deb0`
- `0x1800626d0`
- `0x1800627b0`
- `0x180062d28`
- `0x180063c80`
- `0x18006517c`
- `0x180065c48`
- `0x180070680`
- `0x18007108c`
- `0x1800744cf`
- `0x18008b2f4`
- `0x18008b70c`
- `0x18008c7ec`
- `0x1800c4a0c`
- `0x1800f1ea0`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062e3e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062e5b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062e3e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062e5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006372f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006372f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062ead`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062ead`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180063544`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180063698`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180063544`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180063698`
- `ntdll!RtlInitUnicodeString` at `0x180063081`
- `ntdll!RtlInitUnicodeString` at `0x180063081`
- `ntdll!RtlEnterCriticalSection` at `0x1800635b9`
- `ntdll!RtlEnterCriticalSection` at `0x18006374d`
- `ntdll!RtlEnterCriticalSection` at `0x1800635b9`
- `ntdll!RtlEnterCriticalSection` at `0x18006374d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800635f2`
- `ntdll!RtlLeaveCriticalSection` at `0x180063628`
- `ntdll!RtlLeaveCriticalSection` at `0x18006377b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800635f2`
- `ntdll!RtlLeaveCriticalSection` at `0x180063628`
- `ntdll!RtlLeaveCriticalSection` at `0x18006377b`
- `SspiCli!CredMarshalTargetInfo` at `0x180063427`
- `SspiCli!CredMarshalTargetInfo` at `0x180063427`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x180063569`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x180063569`

## string_xrefs

- `0x180063444`: `Failed to read credentials from the cred mgr 0x%x.\n`

## pseudocode

```c

```
