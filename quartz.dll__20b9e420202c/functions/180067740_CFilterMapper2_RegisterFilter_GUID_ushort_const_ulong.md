# CFilterMapper2::RegisterFilter(_GUID,ushort const *,ulong)

- ea: `0x180067740`
- end: `0x180067971`
- name: `?RegisterFilter@CFilterMapper2@@EEAAJU_GUID@@PEBGK@Z`
- size: `561`
- prototype: `int(CFilterMapper2 *__hidden this, struct _GUID *__struct_ptr, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004924`
- `0x1800388a0`
- `0x180065b20`
- `0x180066aa8`
- `0x180067740`
- `0x180068154`
- `0x1800681e4`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18006783f`
- `KERNEL32!LeaveCriticalSection` at `0x18006792b`
- `KERNEL32!LeaveCriticalSection` at `0x18006793f`
- `KERNEL32!LeaveCriticalSection` at `0x18006783f`
- `KERNEL32!LeaveCriticalSection` at `0x18006792b`
- `KERNEL32!LeaveCriticalSection` at `0x18006793f`
- `KERNEL32!EnterCriticalSection` at `0x180067791`
- `KERNEL32!EnterCriticalSection` at `0x180067791`
- `ADVAPI32!RegCloseKey` at `0x18006782c`
- `ADVAPI32!RegCloseKey` at `0x1800678b0`
- `ADVAPI32!RegCloseKey` at `0x180067904`
- `ADVAPI32!RegCloseKey` at `0x18006791a`
- `ADVAPI32!RegCloseKey` at `0x18006782c`
- `ADVAPI32!RegCloseKey` at `0x1800678b0`
- `ADVAPI32!RegCloseKey` at `0x180067904`
- `ADVAPI32!RegCloseKey` at `0x18006791a`
- `ole32!StringFromGUID2` at `0x1800677c7`
- `ole32!StringFromGUID2` at `0x1800677c7`

## string_xrefs

- `0x180067860`: `CLSID`

## pseudocode

```c

```
