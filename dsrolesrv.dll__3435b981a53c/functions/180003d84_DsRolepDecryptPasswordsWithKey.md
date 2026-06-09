# DsRolepDecryptPasswordsWithKey

- ea: `0x180003d84`
- end: `0x180003fa9`
- name: `DsRolepDecryptPasswordsWithKey`
- size: `549`
- prototype: `ULONG __fastcall(__int64, __int64, unsigned int, __int64, _OWORD *)`
- caller_count: `5`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180005400`
- `0x1800058a0`
- `0x180005e40`
- `0x1800065a0`
- `0x180006c30`

## callees

- `0x180003458`
- `0x18000349c`
- `0x1800034e4`
- `0x18000350c`
- `0x180003570`
- `0x180003d84`
- `0x18002c012`
- `0x18002c050`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x180003e88`
- `bcrypt!BCryptDestroyKey` at `0x180003e88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f6b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003eb7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f1a`
- `ntdll!RtlNtStatusToDosError` at `0x180003de6`
- `ntdll!RtlNtStatusToDosError` at `0x180003de6`
- `ntdll!RtlInitUnicodeString` at `0x180003e1f`
- `ntdll!RtlInitUnicodeString` at `0x180003f76`
- `ntdll!RtlInitUnicodeString` at `0x180003e1f`
- `ntdll!RtlInitUnicodeString` at `0x180003f76`
- `CRYPTBASE!SystemFunction029` at `0x180003dda`
- `CRYPTBASE!SystemFunction029` at `0x180003dda`
- `CRYPT32!CryptProtectMemory` at `0x180003f0d`
- `CRYPT32!CryptProtectMemory` at `0x180003f0d`

## pseudocode

```c

```
