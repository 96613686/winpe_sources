# fcicb_GetOpenInfo

- ea: `0x18002a900`
- end: `0x18002aaa6`
- name: `fcicb_GetOpenInfo`
- size: `422`
- prototype: `INT_PTR __cdecl(LPSTR pszName, USHORT *pdate, USHORT *ptime, USHORT *pattribs, int *err, void *pv)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x18002a900`
- `0x18002ab00`
- `0x180055550`
- `0x180055610`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002a9c3`
- `msvcrt!_wcsicmp` at `0x18002a9c3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002a955`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002a9ab`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002a955`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002a9ab`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18002a9ea`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18002a9ea`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18002aa04`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18002aa04`
- `KERNEL32!FileTimeToDosDateTime` at `0x18002aa14`
- `KERNEL32!FileTimeToDosDateTime` at `0x18002aa14`

## pseudocode

```c

```
