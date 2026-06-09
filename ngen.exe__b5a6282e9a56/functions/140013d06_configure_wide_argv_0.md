# _configure_wide_argv_0

- ea: `0x140013d06`
- end: `0x140013d0c`
- name: `_configure_wide_argv_0`
- size: `6`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140012f60`

## import_xrefs

- `ucrtbase_clr0400!_configure_wide_argv` at `0x140013d06`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl configure_wide_argv_0(_crt_argv_mode mode)
{
  return _configure_wide_argv(mode);
}

```

## disassembly

```asm
0x140013d06  jmp     cs:__imp__configure_wide_argv
```
