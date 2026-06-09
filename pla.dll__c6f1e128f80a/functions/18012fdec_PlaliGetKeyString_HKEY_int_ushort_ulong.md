# PlaliGetKeyString(HKEY__ *,int,ushort * *,ulong *)

- ea: `0x18012fdec`
- end: `0x1801303e6`
- name: `?PlaliGetKeyString@@YAJPEAUHKEY__@@HPEAPEAGPEAK@Z`
- size: `1530`
- prototype: `__int64 __fastcall(HKEY hKey, int, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012e11c`

## callees

- `0x180001580`
- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x1800ac7a4`
- `0x18012dc60`
- `0x18012fdec`
- `0x1801317fc`
- `0x180132bc8`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801301d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801301d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013037f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013037f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013038d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013038d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180130374`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180130374`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801303b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801303b4`
- `CRYPT32!CryptUnprotectData` at `0x1801301c7`
- `CRYPT32!CryptUnprotectData` at `0x1801301c7`

## string_xrefs

- `0x18012ff49`: `EOF Command File`
- `0x18012ff53`: `Command File`

## pseudocode

```c

```
