# GetLastError_0

- ea: `0x1400023a2`
- end: `0x1400023a8`
- name: `GetLastError_0`
- size: `6`
- prototype: `DWORD __stdcall()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000488c`
- `0x140004dd4`
- `0x1400050a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400023a2`

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
0x1400023a2  jmp     cs:__imp_GetLastError
```
