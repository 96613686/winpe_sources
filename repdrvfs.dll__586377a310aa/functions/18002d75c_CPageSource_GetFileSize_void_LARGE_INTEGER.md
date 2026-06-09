# CPageSource::GetFileSize(void *,_LARGE_INTEGER *)

- ea: `0x18002d75c`
- end: `0x18002d7ee`
- name: `?GetFileSize@CPageSource@@QEAAKPEAXPEAT_LARGE_INTEGER@@@Z`
- size: `146`
- prototype: `DWORD __fastcall(CPageSource *this, void *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180040e24`

## callees

- `0x1800012b8`
- `0x18002d75c`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002d77c`
- `wbemcomn!GetMemLogObject` at `0x18002d77c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d790`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002d790`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002d768`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002d768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7df`

## pseudocode

```c

```
