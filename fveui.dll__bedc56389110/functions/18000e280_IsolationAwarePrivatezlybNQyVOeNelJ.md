# IsolationAwarePrivatezlybNQyVOeNelJ

- ea: `0x18000e280`
- end: `0x18000e287`
- name: `IsolationAwarePrivatezlybNQyVOeNelJ`
- size: `7`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000df94`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18000e280`

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
0x18000e280  jmp     cs:__imp_LoadLibraryW
```
