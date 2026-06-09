# KernelTriageDumpTargetInfo::AddContextToMemoryBlock(unsigned __int64,ulong,char *,ulong,ulong,TriageMemoryBlock * *)

- ea: `0x18022d6b4`
- end: `0x18022d9f0`
- name: `?AddContextToMemoryBlock@KernelTriageDumpTargetInfo@@QEAAK_KKPEADKKPEAPEAUTriageMemoryBlock@@@Z`
- size: `828`
- prototype: `unsigned int(KernelTriageDumpTargetInfo *__hidden this, unsigned __int64, unsigned int, char *, unsigned int, unsigned int, struct TriageMemoryBlock **)`
- caller_count: `6`
- callee_count: `7`
- tags: ``

## callers

- `0x180220960`
- `0x180221090`
- `0x180221340`
- `0x18022138c`
- `0x18022146c`
- `0x180221b0c`

## callees

- `0x180071a60`
- `0x1800c1cd8`
- `0x1800f0f40`
- `0x18016cdec`
- `0x180224eb8`
- `0x180225e60`
- `0x18022d6b4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x18022d946`
- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x18022d946`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022d74d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022d9a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022d74d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022d9a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022d9bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022d9bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022d764`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022d764`

## string_xrefs

- `0x18022d7d6`: `KernelTriageDumpTargetInfo::AddContextToMemoryBlock::        ==> Failed to read signature (0x%I64x) offset %x\n`
- `0x18022d8a9`: `KernelTriageDumpTargetInfo::AddContextToMemoryBlock::        ==> Failed to read ContextTypeInfo field(0x%I64x)\n`
- `0x18022d85a`: `KernelTriageDumpTargetInfo::AddContextToMemoryBlock::        ==> Failed to read ContextTypeInfoPtr field(0x%I64x,0x%I64x)\n`
- `0x18022d90b`: `KernelTriageDumpTargetInfo::AddContextToMemoryBlock::        ==> Failed to read context name (0x%I64x)\n`

## pseudocode

```c

```
