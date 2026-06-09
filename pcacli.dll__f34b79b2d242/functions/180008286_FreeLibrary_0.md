# FreeLibrary_0

- ea: `0x180008286`
- end: `0x18000828c`
- name: `FreeLibrary_0`
- size: `6`
- prototype: `BOOL __stdcall(HMODULE hLibModule)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800032f0`
- `0x180004790`
- `0x1800054f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008286`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall FreeLibrary_0(HMODULE hLibModule)
{
  return FreeLibrary(hLibModule);
}

```

## disassembly

```asm
0x180008286  jmp     cs:__imp_FreeLibrary
```
