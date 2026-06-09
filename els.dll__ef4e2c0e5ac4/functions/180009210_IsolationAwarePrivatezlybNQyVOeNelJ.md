# IsolationAwarePrivatezlybNQyVOeNelJ

- ea: `0x180009210`
- end: `0x180009217`
- name: `IsolationAwarePrivatezlybNQyVOeNelJ`
- size: `7`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180009210`

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
0x180009210  jmp     cs:__imp_LoadLibraryW
```
