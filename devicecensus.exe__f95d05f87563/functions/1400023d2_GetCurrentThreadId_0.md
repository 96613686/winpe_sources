# GetCurrentThreadId_0

- ea: `0x1400023d2`
- end: `0x1400023d8`
- name: `GetCurrentThreadId_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140006ef4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400023d2`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetCurrentThreadId_0()
{
  return GetCurrentThreadId();
}

```

## disassembly

```asm
0x1400023d2  jmp     cs:__imp_GetCurrentThreadId
```
