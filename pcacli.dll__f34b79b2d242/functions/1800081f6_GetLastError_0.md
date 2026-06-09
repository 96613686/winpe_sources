# GetLastError_0

- ea: `0x1800081f6`
- end: `0x1800081fc`
- name: `GetLastError_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004790`
- `0x180008d4c`
- `0x1800092ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081f6`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall GetLastError_0()
{
  return GetLastError();
}

```

## disassembly

```asm
0x1800081f6  jmp     cs:__imp_GetLastError
```
