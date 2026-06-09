# LoadLibraryW_0

- ea: `0x140002c30`
- end: `0x140002c36`
- name: `LoadLibraryW_0`
- size: `6`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140002c30`

## pseudocode

```c
// attributes: thunk
HMODULE __stdcall LoadLibraryW_0(LPCWSTR lpLibFileName)
{
  return LoadLibraryW(lpLibFileName);
}

```

## disassembly

```asm
0x140002c30  jmp     cs:__imp_LoadLibraryW
```
