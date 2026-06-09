# KernelTriageDumpTargetInfo::AddWdfObjectAndContextsToMemoryBlock(unsigned __int64,TriageMemoryBlock * *,int)

- ea: `0x18022d9f8`
- end: `0x18022dc91`
- name: `?AddWdfObjectAndContextsToMemoryBlock@KernelTriageDumpTargetInfo@@QEAAK_KPEAPEAUTriageMemoryBlock@@H@Z`
- size: `665`
- prototype: `unsigned int(KernelTriageDumpTargetInfo *__hidden this, unsigned __int64, struct TriageMemoryBlock **, int)`
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x180220414`
- `0x180220be8`
- `0x180221090`
- `0x18022146c`
- `0x180222f48`
- `0x180223528`
- `0x180224294`
- `0x18022d10c`
- `0x18022dc98`
- `0x18022e024`

## callees

- `0x180071a60`
- `0x1800c1cd8`
- `0x18016cdec`
- `0x180224eb8`
- `0x18022d9f8`
- `0x18022e518`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022da66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022dc55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022da66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022dc55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022dc69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022dc69`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022da7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022da7d`

## string_xrefs

- `0x18022dc3f`: `KernelTriageDumpTargetInfo::AddWdfObjectAndContextsToMemoryBlock::        ==> Failed to read ContextTypeInfoPtr field(0x%I64x,0x%I64x)\n`
- `0x18022dc2a`: `KernelTriageDumpTargetInfo::AddWdfObjectAndContextsToMemoryBlock::        ==> Failed to read ContextTypeInfo field(0x%I64x)\n`

## pseudocode

```c

```
