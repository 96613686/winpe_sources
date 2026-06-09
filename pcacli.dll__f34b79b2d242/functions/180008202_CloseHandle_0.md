# CloseHandle_0

- ea: `0x180008202`
- end: `0x180008208`
- name: `CloseHandle_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hObject)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180007200`
- `0x180008d4c`
- `0x1800092ac`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008202`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall CloseHandle_0(HANDLE hObject)
{
  return CloseHandle(hObject);
}

```

## disassembly

```asm
0x180008202  jmp     cs:__imp_CloseHandle
```
