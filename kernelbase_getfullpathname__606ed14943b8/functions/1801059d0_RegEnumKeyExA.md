# RegEnumKeyExA

- ea: `0x1801059d0`
- end: `0x180105cbe`
- name: `RegEnumKeyExA`
- size: `750`
- prototype: `LSTATUS __stdcall(HKEY hKey, DWORD dwIndex, LPSTR lpName, LPDWORD lpcchName, LPDWORD lpReserved, LPSTR lpClass, LPDWORD lpcchClass, PFILETIME lpftLastWriteTime)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18012aa3c`
- `0x180148bb0`

## callees

- `0x18005e7e0`
- `0x18005feb0`
- `0x180062d50`
- `0x1801059d0`
- `0x180136e28`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x180105b83`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180105ca3`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180105b83`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180105ca3`
- `ntdll!RtlNtStatusToDosError` at `0x180105bba`
- `ntdll!RtlNtStatusToDosError` at `0x180105bba`
- `ntdll!RtlFreeHeap` at `0x180105ba6`
- `ntdll!RtlFreeHeap` at `0x180105c65`
- `ntdll!RtlFreeHeap` at `0x180105ba6`
- `ntdll!RtlFreeHeap` at `0x180105c65`
- `ntdll!RtlAllocateHeap` at `0x180105acd`
- `ntdll!RtlAllocateHeap` at `0x180105acd`
- `ext-ms-win-advapi32-registry-l1-1-0!RemoteRegEnumKeyWrapper` at `0x1801a2626`
- `ext-ms-win-advapi32-registry-l1-1-0!RemoteRegEnumKeyWrapper` at `0x1801a2626`

## pseudocode

```c

```
