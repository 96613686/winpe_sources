# IsolationAwarePrivatezlybNQyVOeNelJ

- ea: `0x180007c60`
- end: `0x180007c67`
- name: `IsolationAwarePrivatezlybNQyVOeNelJ`
- size: `7`
- prototype: `HMODULE __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180007918`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180007c60`

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
0x180007c60  jmp     cs:__imp_LoadLibraryW
```
