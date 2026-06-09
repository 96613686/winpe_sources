# _configure_narrow_argv_0

- ea: `0x1800050da`
- end: `0x1800050e0`
- name: `_configure_narrow_argv_0`
- size: `6`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180001564`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_configure_narrow_argv` at `0x1800050da`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl configure_narrow_argv_0(_crt_argv_mode mode)
{
  return _configure_narrow_argv(mode);
}

```

## disassembly

```asm
0x1800050da  jmp     cs:__imp__configure_narrow_argv
```
