# CloseHandle_0

- ea: `0x1400023ae`
- end: `0x1400023b4`
- name: `CloseHandle_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hObject)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400042c0`
- `0x14000488c`
- `0x1400050a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400023ae`

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
0x1400023ae  jmp     cs:__imp_CloseHandle
```
