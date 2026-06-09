# IsolationAwarePrivatezlybNQyVOeNelJ

- ea: `0x1800088e0`
- end: `0x1800088e7`
- name: `IsolationAwarePrivatezlybNQyVOeNelJ`
- size: `7`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800088e0`

## pseudocode

```c
// attributes: thunk
HMODULE __stdcall IsolationAwarePrivatezlybNQyVOeNelJ(LPCWSTR lpLibFileName)
{
  return LoadLibraryW(lpLibFileName);
}

```

## disassembly

```asm
0x1800088e0  jmp     cs:__imp_LoadLibraryW
```
