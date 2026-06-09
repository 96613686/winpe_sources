# CFilterMapper2::RegisterPinType(_GUID,ushort const *,_GUID,_GUID)

- ea: `0x180067dd0`
- end: `0x180067f93`
- name: `?RegisterPinType@CFilterMapper2@@EEAAJU_GUID@@PEBG00@Z`
- size: `451`
- prototype: `int(CFilterMapper2 *__hidden this, struct _GUID *__struct_ptr, const unsigned __int16 *, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004924`
- `0x1800388a0`
- `0x180065b20`
- `0x1800662f4`
- `0x180066aa8`
- `0x180067dd0`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180067f65`
- `KERNEL32!LeaveCriticalSection` at `0x180067f65`
- `KERNEL32!EnterCriticalSection` at `0x180067e7e`
- `KERNEL32!EnterCriticalSection` at `0x180067e7e`
- `ADVAPI32!RegCloseKey` at `0x180067f4d`
- `ADVAPI32!RegCloseKey` at `0x180067f4d`
- `ole32!StringFromGUID2` at `0x180067e29`
- `ole32!StringFromGUID2` at `0x180067e42`
- `ole32!StringFromGUID2` at `0x180067e5b`
- `ole32!StringFromGUID2` at `0x180067e29`
- `ole32!StringFromGUID2` at `0x180067e42`
- `ole32!StringFromGUID2` at `0x180067e5b`

## string_xrefs

- `0x180067eca`: `CLSID`
- `0x180067f03`: `CLSID`

## pseudocode

```c

```
