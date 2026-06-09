# WINRT_IMPL_HeapFree

- ea: `0x18000343c`
- end: `0x180003442`
- name: `WINRT_IMPL_HeapFree`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hHeap, DWORD dwFlags, LPVOID lpMem)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004ee4`
- `0x18000a624`
- `0x180015c70`
- `0x180015f40`
- `0x180016d5b`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000343c`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall WINRT_IMPL_HeapFree(HANDLE hHeap, DWORD dwFlags, LPVOID lpMem)
{
  return HeapFree(hHeap, dwFlags, lpMem);
}

```

## disassembly

```asm
0x18000343c  jmp     cs:__imp_HeapFree
```
