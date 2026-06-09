# CFilterMapper2::UnregisterFilter(_GUID const *,ushort const *,_GUID const &)

- ea: `0x180068360`
- end: `0x1800684fe`
- name: `?UnregisterFilter@CFilterMapper2@@EEAAJPEBU_GUID@@PEBGAEBU2@@Z`
- size: `414`
- prototype: `int(CFilterMapper2 *__hidden this, const struct _GUID *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800388a0`
- `0x180065b20`
- `0x180068360`
- `0x1800691b8`
- `0x180069534`
- `0x180069594`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800684d2`
- `KERNEL32!LeaveCriticalSection` at `0x1800684d2`
- `KERNEL32!EnterCriticalSection` at `0x18006839d`
- `KERNEL32!EnterCriticalSection` at `0x18006839d`
- `ole32!StringFromGUID2` at `0x1800683c9`
- `ole32!StringFromGUID2` at `0x1800683e5`
- `ole32!StringFromGUID2` at `0x1800683c9`
- `ole32!StringFromGUID2` at `0x1800683e5`

## string_xrefs

- `0x180068404`: `CLSID`

## pseudocode

```c

```
