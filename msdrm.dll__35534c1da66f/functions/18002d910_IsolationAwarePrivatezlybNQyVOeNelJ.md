# IsolationAwarePrivatezlybNQyVOeNelJ

- ea: `0x18002d910`
- end: `0x18002d917`
- name: `IsolationAwarePrivatezlybNQyVOeNelJ`
- size: `7`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18002d7b8`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18002d910`

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
0x18002d910  jmp     cs:__imp_LoadLibraryW
```
