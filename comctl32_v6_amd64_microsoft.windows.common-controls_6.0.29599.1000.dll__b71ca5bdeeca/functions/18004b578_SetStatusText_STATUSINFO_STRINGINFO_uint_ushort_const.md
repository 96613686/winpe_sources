# SetStatusText(STATUSINFO *,STRINGINFO *,uint,ushort const *)

- ea: `0x18004b578`
- end: `0x18004b730`
- name: `?SetStatusText@@YAHPEAUSTATUSINFO@@PEAUSTRINGINFO@@IPEBG@Z`
- size: `440`
- prototype: `int(struct STATUSINFO *, struct STRINGINFO *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18004b4e4`

## callees

- `0x180016c78`
- `0x18004b578`
- `0x180114520`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b5c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b667`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b5c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b667`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b68c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b68c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b5d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b5d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004b657`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18004b657`
- `USER32!GetClientRect` at `0x18004b605`
- `USER32!GetClientRect` at `0x18004b605`
- `USER32!UpdateWindow` at `0x18004b708`
- `USER32!UpdateWindow` at `0x18004b708`
- `USER32!InvalidateRect` at `0x18004b638`
- `USER32!InvalidateRect` at `0x18004b638`

## pseudocode

```c

```
