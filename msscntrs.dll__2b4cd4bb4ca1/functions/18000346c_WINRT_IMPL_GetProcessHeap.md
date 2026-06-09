# WINRT_IMPL_GetProcessHeap

- ea: `0x18000346c`
- end: `0x180003472`
- name: `WINRT_IMPL_GetProcessHeap`
- size: `6`
- prototype: `HANDLE __stdcall()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180004ee4`
- `0x18000a624`
- `0x18000a78c`
- `0x180015c70`
- `0x180015f40`
- `0x180016d5b`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000346c`

## pseudocode

```c
// attributes: thunk
HANDLE __stdcall WINRT_IMPL_GetProcessHeap()
{
  return GetProcessHeap();
}

```

## disassembly

```asm
0x18000346c  jmp     cs:__imp_GetProcessHeap
```
