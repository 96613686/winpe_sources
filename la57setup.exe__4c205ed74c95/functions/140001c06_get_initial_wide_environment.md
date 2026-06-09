# _get_initial_wide_environment

- ea: `0x140001c06`
- end: `0x140001c0c`
- name: `_get_initial_wide_environment`
- size: `6`
- prototype: `wchar_t **__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_initial_wide_environment` at `0x140001c06`

## pseudocode

```c
// attributes: thunk
wchar_t **__cdecl get_initial_wide_environment()
{
  return _o__get_initial_wide_environment();
}

```

## disassembly

```asm
0x140001c06  jmp     cs:__imp__o__get_initial_wide_environment
```
