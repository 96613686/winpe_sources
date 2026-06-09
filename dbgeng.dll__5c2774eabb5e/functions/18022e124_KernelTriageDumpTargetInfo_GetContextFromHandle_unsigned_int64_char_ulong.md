# KernelTriageDumpTargetInfo::GetContextFromHandle(unsigned __int64,char *,ulong *)

- ea: `0x18022e124`
- end: `0x18022e3a2`
- name: `?GetContextFromHandle@KernelTriageDumpTargetInfo@@QEAA_K_KPEADPEAK@Z`
- size: `638`
- prototype: `unsigned __int64 __fastcall(KernelTriageDumpTargetInfo *__hidden this, unsigned __int64, char *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180220be8`

## callees

- `0x180071a60`
- `0x1800c1cd8`
- `0x1800f0f40`
- `0x18016cdec`
- `0x180225e60`
- `0x18022e124`
- `0x18022e518`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x18022e2bc`
- `api-ms-win-crt-string-l1-1-0!_strnicmp` at `0x18022e2bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e19e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e360`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e19e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18022e360`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022e374`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18022e374`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e1b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18022e1b5`

## string_xrefs

- `0x18022e335`: `KernelTriageDumpTargetInfo::GetContextFromHandle::        ==> Failed to read ContextTypeInfo field(0x%I64x)\n`
- `0x18022e351`: `KernelTriageDumpTargetInfo::GetContextFromHandle::        ==> Failed to read ContextTypeInfoPtr field(0x%I64x,0x%I64x)\n`

## pseudocode

```c

```
