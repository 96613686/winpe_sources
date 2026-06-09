# _o__configure_narrow_argv_0

- ea: `0x140001d7e`
- end: `0x140001d84`
- name: `_o__configure_narrow_argv_0`
- size: `6`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1400011b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configure_narrow_argv` at `0x140001d7e`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl o__configure_narrow_argv_0(_crt_argv_mode mode)
{
  return _configure_narrow_argv(mode);
}

```

## disassembly

```asm
0x140001d7e  jmp     cs:__imp__configure_narrow_argv
```
