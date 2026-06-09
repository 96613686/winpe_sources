# IsolationAwarePrivatezlybNQyVOeNelJ

- ea: `0x1800bf780`
- end: `0x1800bf787`
- name: `IsolationAwarePrivatezlybNQyVOeNelJ`
- size: `7`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800bf468`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800bf780`

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
0x1800bf780  jmp     cs:__imp_LoadLibraryW
```
